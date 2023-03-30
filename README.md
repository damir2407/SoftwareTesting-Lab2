# Лабораторная №2 - по ТПО 
## Задание
Провести интеграционное тестирование программы, осуществляющей вычисление системы функций (в соответствии с вариантом).

![image](https://user-images.githubusercontent.com/70958074/228808991-86f8da7e-4eee-4b86-8e86-67e2fcadea0a.png)


```
x <= 0 : (((((((sec(x) * sec(x)) ^ 2) * sec(x)) - (sec(x) + sec(x))) - csc(x)) / ((tan(x) + sec(x)) * cos(x))) / (((csc(x) - (tan(x) + (cot(x) - sec(x)))) - ((((cot(x) - csc(x)) * tan(x)) / cos(x)) - cot(x))) * ((cos(x) + tan(x)) ^ 2)))
x > 0 : (((((ln(x) + log_3(x)) * log_3(x)) / log_5(x)) + ((log_2(x) - log_3(x)) * log_10(x))) ^ 2)
```

### Правила выполнения работы:
1. Все составляющие систему функции (как тригонометрические, так и логарифмические) должны быть выражены через базовые (тригонометрическая зависит от варианта; логарифмическая - натуральный логарифм). 
2. Структура приложения, тестируемого в рамках лабораторной работы, должна выглядеть следующим образом (пример приведён для базовой тригонометрической функции sin(x)):  
3. ![image](https://user-images.githubusercontent.com/70958074/228809235-e74a6fb7-4058-4e18-b48b-a51c6244578c.png)

4. Обе "базовые" функции (в примере выше - sin(x) и ln(x)) должны быть реализованы при помощи разложения в ряд с задаваемой погрешностью. Использовать тригонометрические / логарифмические преобразования для упрощения функций ЗАПРЕЩЕНО. 
5. Для КАЖДОГО модуля должны быть реализованы табличные заглушки. При этом, необходимо найти область допустимых значений функций, и, при необходимости, определить взаимозависимые точки в модулях. 
6. Разработанное приложение должно позволять выводить значения, выдаваемое любым модулем системы, в сsv файл вида «X, Результаты модуля (X)», позволяющее произвольно менять шаг наращивания Х. Разделитель в файле csv можно использовать произвольный.

## Полезная информация
+ [JUnit 5](https://www.baeldung.com/parameterized-tests-junit-5)
+ [График системы](https://www.desmos.com/calculator/pa0j2wg3wb)
+ [Mockito - annotations](https://www.baeldung.com/mockito-annotations)
+ [Mockito - использование](https://java-online.ru/junit-mockito.xhtml)
+ [BigDecimal / BigInteger](https://metanit.com/java/tutorial/12.2.php)
+ [WolframAlpha](https://www.wolframalpha.com/)

## Шаблон тестирующего метода
```
@Test
@DisplayName("Test name")
void testName() {
    assertAll(
        () -> assertEquals(1, 1)
    );
}
```

```
@ParameterizedTest
@DisplayName("Parameterized test name")
@ValueSource(its = {1})
void parameterizedTestName(int param) {
    assertAll(
        () -> assertEquals(1, param)
    );
}
```
