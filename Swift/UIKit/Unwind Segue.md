## Unwind Segue



Unwind Segue — это способ вернуться назад на предыдущий экран (`UIViewController`) в `Storyboard`, не создавая новый экземпляр.

Обычные `Segue` создают новый экран (`push` или `present`), а Unwind Segue позволяет вернуться назад, как `popViewController()`.



####  Когда использовать Unwind Segue?

✔ Если экран открыт через `push` или `present` и нужно вернуться назад.
✔ Если нужно передать данные обратно (`Delegate` или `Closure` не нужны).
✔ Если нужно вернуться на конкретный экран, даже если он не был вызван напрямую.



#### Как создать Unwind Segue?

1. Создай метод Unwind в `ViewController`, куда нужно вернуться

В `ViewController`, на который ты хочешь вернуться (например, `FirstViewController`), создай метод с `@IBAction`:

```swift
@IBAction func unwindToFirstVC(_ segue: UIStoryboardSegue) {
    print("Возвращаемся назад через Unwind Segue!")
}
```

Метод должен быть `@IBAction`, иначе `Storyboard` его не увидит.

Метод принимает `UIStoryboardSegue`, но тело метода может быть пустым.

Этот метод не вызывается вручную, он нужен только для `Storyboard`.



2. Подключи кнопку в `SecondViewController`

Теперь в `SecondViewController` (откуда нужно вернуться) свяжи кнопку с `Exit` в `Storyboard`:

- Открой `Storyboard` и выбери кнопку "Назад".
- Зажми `Control (⌃)` и перетащи линию от кнопки к значку `Exit` (сверху экрана).
- В появившемся списке выбери `unwindToFirstVC`.

Теперь при нажатии кнопки вызовется Unwind Segue, и экран вернётся назад!



3. Как передать данные через Unwind Segue?

Ты можешь передавать данные из `SecondViewController` в `FirstViewController`:

```swift
@IBAction func unwindToFirstVC(_ segue: UIStoryboardSegue) {
    if let sourceVC = segue.source as? SecondViewController {
        print("Получены данные: \(sourceVC.someData)")
    }
}
```

Этот код получает доступ к `SecondViewController` через `segue.source` и передаёт данные назад.
