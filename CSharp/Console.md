## Console



```c#
Console.Write("Введите логин: ");

Console.WriteLine("Выберите желаемое действие:");

Console.WriteLine("({0}). {1}", i + 1, BD.ViewActions(User.ActionsList[i]));

string name = Console.ReadLine();

ConsoleKey cki = Console.ReadKey(true).Key;

Console.Clear();
```

