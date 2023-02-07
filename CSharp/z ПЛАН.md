

Что надо сделать:

1. using
2. трансформация свойств в поля
3. Ссылочные и значимые типы
4. Параметры в методах, возвращаемый результат, (ref, out (+отбрасывание), params, параметры по умолчанию)
5. отбрасывание у кортежей
6. linq staff.FirstOrDefault(e => e.Name == employee.Name) != (null, null)
7. Интерфейсы для структуры
8. GetHashCode
9. IEqualityComparer
10. Чтобы создать экземпляр [анонимного типа](https://docs.microsoft.com/ru-ru/dotnet/csharp/fundamentals/types/anonymous-types), используйте оператор `new` и синтаксис инициализации объекта:...
11. Приведение типов. is и as, сопоставление шаблонов с is (паттерн матч). Доункаст, абкаст
12. Только в интерфейсах и делегатах можно использовать ковариантность и контравариантность.
13. Деревья выражений.
14. Матчинг




Прочее

Комплекты .NET SDK https://dotnet.microsoft.com/en-us/download/dotnet

Список установленных комплектов SDK `dotnet --list-sdks`

Список пакетов в проекте `dotnet list package`

Пакет инструментов dotnet-ef https://www.nuget.org/packages/dotnet-ef/

Пакет инструментов LibMan https://www.nuget.org/packages/Microsoft.Web.LibraryManager.Cli

```powershell
dotnet tool uninstall --global Microsoft.Web.LibraryManager.Cli
dotnet tool install --global Microsoft.Web.LibraryManager.Cli --version 2.1.174

libman init -p cdnjs
libman install twitter-bootstrap@4.6.1 -d wwwroot/lib/twitter-bootstrap
```

