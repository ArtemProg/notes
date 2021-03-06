### null



#### Оператор объединения с null

```c#
Console.WriteLine(str ?? "Данные не заданы");
```



#### Оператор присвоения объединения со значением null

Реализовано в C# 8

```c#
str ??= "Данные не заданы";
```



#### Оператор условного null (элвис оператор): ?. и ?[]

Комбинируем с оператором объединения с null

```c#
int[] arr = null;
arr?.Sum()
Console.WriteLine("Сумма элементов массива " + (arr?.Sum() ?? 0));
```

Пример 2:

```c#
Person person = GetPerson();
Console.WriteLine(person?.Contacts?.PhoneNumber ?? "нет данных");
```



### Null совместимые значимые типы Nullable

Зачем это надо, какой смысл: данные могут отсутствовать во внешних источниках. К примеру в базе данных по пользователю могут быть не заполнены некоторые поля (дата рождения, пол, возраст,...), т.е. содержать значение null.

```c#
int? i = null;
int? j = i + 4; // результат j = null
```

При этом у значимого типа появляются два свойства:

- `HasValue` - Тип: bool - Указывает заполненно ли значение.
- `Value` - Тип: тип переменной по умолчанию - Доступно, только когда значение заполнено.

```c#
int? i = 5;
Console.WriteLine(i == null); // False
Console.WriteLine(i.HasValue); // True
Console.WriteLine(i.GetValueOrDefault()); // 5
Console.WriteLine(i.GetValueOrDefault(10)); // 5
Console.WriteLine(i ?? 55); // 5
Console.WriteLine(i.Value); // 5
```



При сравнении операндов один из которых равен `null` - результатом сравнения всегда будет `false`.

```c#
int? a = null;
int? b = 5;
if (a >= b) { ;} // false
```

Сравнивать операнды (`Nullable`) есть смысл только для проверки - оба ли содержат `null`? И если оба операнда содержат `null`, то результатом сравнения будет `true`.

```c#
int? a = null;
int? b = null;
if (a == b) { ;} // true
```



На самом деле така конструкция под капотом имеет следующий вид:

```c#
Nullable<int> i = null;
```

