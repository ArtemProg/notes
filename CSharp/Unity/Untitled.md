Направление



Вычисляет угол поворота

```c#
public Quaternion Rotation(Vector3 point1, Vector3 point2)
{
    Vector3 dir = point2 - point1;
    float angleDirection = Mathf.Atan2(dir.y, dir.x) * Mathf.Rad2Deg;
    Quaternion rotation = Quaternion.AngleAxis(angleDirection, Vector3.forward);
    return rotation;
}
```

https://docs.unity3d.com/ru/530/ScriptReference/Mathf.Atan2.html

https://docs.unity3d.com/ScriptReference/Mathf.Rad2Deg.html

https://poqxert.ru/blog/unity/tutorials/matematika/matematika-unity-urok-4-mathf-dva-arktangensa

https://docs.unity3d.com/ScriptReference/Transform-forward.html



Вычисление дистанции между точками

```c#
float distance = Vector2.Distance(point1, point2)
```



Определение пересечений

```c#
RaycastHit2D hit = Physics2D.Raycast(mousePoint, Vector2.zero);
```

