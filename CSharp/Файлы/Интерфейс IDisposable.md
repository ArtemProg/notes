## Интерфейс IDisposable

Дает метод освобождения распределенных ресурсов.

```c#
public interface IDisposable
{
	void Dispose();
}
```

Любой класс, реализующий интерфейс IDisposable, немедленно освобождает любые задействованные ресурсы после вызова его метода Dispose(). Это последнее, что делается перед завершением работы с объектом.



### Инструкция using

Данная инструкция применяется только для классов, которые реализуют интерфейс IDisposable, и автоматически вызывает метод Dispose для освобождения ресурсов.

```c#
string filename = @"C:\Progs\test.txt";
string txt = String.Empty;

using (StreamReader sr = new StreamReader(filename)) {
	txt = sr.ReadToEnd();
}
```

Инструкция using на самом деле является синтаксическим удобством. Во время компиляции языковой компилятор реализует промежуточный язык (IL) для try / finally блока.

```c#
string filename = @"C:\Progs\test.txt";
string txt = String.Empty;

{
	StreamReader sr = new StreamReader(filename);
	try
	{
		txt = sr.ReadToEnd();
	}
	finally
	{
		if (sr != null) sr.Dispose();
	}
}
```



Все потоки имеют закрывающий метод Dispose(). При этом поток, объявленный внутри оператора using, всегда закрывает себя сам. Потоки рекомендуется объявлять внутри оператора using. Это гарантирует, что после завершения работы они будут закрыты.