### Структура DateTime



Для создания нового объекта DateTime также можно использовать конструктор. Пустой конструктор создает начальную дату:
```c#
DateTime date1 = new DateTime();
Console.WriteLine(date1); // 01.01.0001 12:00:00 AM
```



То есть мы получим минимально возможное значение, которое также можно получить следующим образом:
```c#
Console.WriteLine(DateTime.MinValue);
```



Чтобы задать конкретную дату, нужно использовать один из конструкторов, принимающих параметры:
```c#
DateTime date1 = new DateTime(2015, 7, 20); // год - месяц - день
Console.WriteLine(date1); // 20.07.2015 0:00:00
```



Если необходимо получить текущую время и дату, то можно использовать ряд свойств DateTime:
```c#
Console.WriteLine(DateTime.Now);
Console.WriteLine(DateTime.UtcNow);
Console.WriteLine(DateTime.Today);
```



**Метод Parse**

Преобразует строковое представление даты и времени в его эквивалент DateTime.

```c#
Date = DateTime.Parse("11.11.2021");
```



**Метод ToString**

Преобразует значение текущего объекта DateTime в эквивалентное ему строковое представление.

```c#
DateTime date= new DateTime(2015, 7, 20);
Console.WriteLine(date.ToString("dd.MM.yyyy"))
```

