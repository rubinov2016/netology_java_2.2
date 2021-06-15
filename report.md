# Отчёт о тестировании "Precision"
## Краткое описание
26.05.2021 было проведено проверка начисления дополнительного бонуса новым клиентам в приложении "Precision"

На тестирование затрачено: 20 минут

## Раздел дефектов
В результате тестирования выявлены следующие дефекты:

1. Неправильное округление денежных средств с более чем двумя цифрами после запяптой 
      
   [Баг-репорт](https://github.com/rubinov2016/netology_java_2.2/issues/1)
   

## Описание процесса тестирования
В процессе тестирования использовался следующий код:
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
В качестве тестовых данных использовались данные
* переменная regularBonus типа double, значение - 0.3 (30 процентов)
* переменная specialBonus типа double, значение - 0.6 (60 процентов)
* переменная totalBonus для хранения итогового значения - типа double. Ожидаемое значение 0.90 (при арифметическом сложении бонусов) или 0.72 (при умножении бонусов)

### Тестирование производилось в следующем окружении:

* Microsoft Windows [Version 10.0.19042.928]
* openjdk version "11.0.10" 2021-01-19
* OpenJDK Runtime Environment AdoptOpenJDK (build 11.0.10+9)
* OpenJDK 64-Bit Server VM AdoptOpenJDK (build 11.0.10+9, mixed mode)
