## performSegue



`performSegue(withIdentifier:sender:)` — это метод, который запускает переход (Segue) на другой экран программно, а не через `Storyboard`.

Если ты создал `Segue` в `Storyboard`, но хочешь запустить его из кода — используй `performSegue`.



### Как использовать `performSegue`?

Допустим, у тебя есть `Storyboard`, где:

1. У `FirstViewController` есть кнопка **"Next"**.
2. `SecondViewController` связан с `FirstViewController` через `Segue` (нажатие кнопки).
3. У `Segue` есть **Identifier** (например, `"goToSecondVC"`).

```swift
class FirstViewController: UIViewController {
    
    @IBAction func nextButtonTapped(_ sender: UIButton) {
        performSegue(withIdentifier: "goToSecondVC", sender: nil)
    }
}
```

Теперь, при нажатии кнопки "Next", код программно запустит переход на `SecondViewController`.



### Как передать данные при `performSegue`?

Если нужно передать данные **на следующий экран**, переопредели метод `prepare(for:sender:)`.

```swift
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
    if segue.identifier == "goToSecondVC" {
        let destinationVC = segue.destination as! SecondViewController
        destinationVC.receivedText = "Привет, SecondViewController!"
    }
}
```

**Что здесь происходит?**

1. `prepare(for:sender:)` вызывается перед `performSegue`.
2. Проверяем `segue.identifier == "goToSecondVC"`, чтобы убедиться, что это нужный переход.
3. Передаём данные в `destinationVC.receivedText`.



### Как сделать `performSegue` с разными условиями?

Если `performSegue` нужно вызывать **по условиям**, можно так:

```swift
@IBAction func checkAndGo(_ sender: UIButton) {
    let isUserLoggedIn = true
    
    if isUserLoggedIn {
        performSegue(withIdentifier: "goToProfile", sender: nil)
    } else {
        performSegue(withIdentifier: "goToLogin", sender: nil)
    }
}
```

Теперь, если пользователь авторизован, откроется `ProfileViewController`, иначе `LoginViewController`.



### Как отменить `Segue` (запретить переход)?

Если тебе нужно **иногда запрещать переход**, используй `shouldPerformSegue(withIdentifier:sender:)`.

```swift
override func shouldPerformSegue(withIdentifier identifier: String, sender: Any?) -> Bool {
    if identifier == "goToSecretVC" {
        return false  // Запрещаем переход
    }
    return true  // Разрешаем
}
```

Теперь `goToSecretVC` никогда не откроется, даже если вызван `performSegue`.
