# Отчёт о тестировании функционала по начислению дополнительного бонуса новым клиентам.

## Краткое описание

12.05.2021 г. был проведен smoke test функционала по начислению дополнительного бонуса новым клиентам. Тестирование проводилось методом белого ящика.

На тестирование затрачено: 20 минут.

В результате тестирования выявлен следующий дефект:

* [Неточный расчет итоговой суммы бонуса новым клиентам, необходимо округление](https://github.com/AllaKobyzeva/java_1.2.2/issues/1)

## Описание процесса тестирования

В качестве тестовых данных использовался предоставленный код:
```java
public class Main {
public static void main(String[] args) {
double regularBonus = 0.3;
double specialBonus = 0.6;
double totalBonus = regularBonus + specialBonus;
System.out.println(totalBonus);
}
}
```
В процессе тестирования были запущены 2 тест-кейса:
1. Запуск предоставленного кода.
2. Запуск кода с функцией округления:
```java
public class Main {
public static void main(String[] args) {
double regularBonus = 0.3;
double specialBonus = 0.6;
double totalBonus = Math.round((regularBonus + specialBonus) * 100.0) / 100.0;
System.out.println(totalBonus);
}
}
```
Тестирование производилось в следующем окружении:
* Windows 8 x64;
* Java 11.0.10;
* IntelliJ IDEA Community Edition 2021.1.1.