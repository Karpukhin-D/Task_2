# Практическая работа №2: Операторы языка C#
## Выполнил студент группы П25-2.1 Карпухин Дмитрий

### Блок 3.1. Арифметические операторы
---
> * №1. Задача: Вычислите результат выражения int x = 17 / 5; int y = 17 % 5;. Ответ: x = 3, y = 2.
```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 17 / 5;
        int y = 17 % 5;

        Console.WriteLine($"x = {x}, y = {y}");
    }
}
```

> * №2. Задача: Каково значение res после выполнения int a = 5; int res = ++a * 2;? Ответ: res = 12 (префиксный инкремент увеличивает a до 6, затем выполняется умножение).
```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 5;
        int res = ++a * 2;

        Console.WriteLine($"a = {a}");
        Console.WriteLine($"res = {res}");
    }
}
```

> * №3. Задача: Каково значение res после выполнения int a = 5; int res = a++ * 2;? Ответ: res = 10 (постфиксный инкремент использует исходное значение 5, затем a становится равным 6).
```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 5;
        int res = a++ * 2;

        Console.WriteLine($"a = {a}");
        Console.WriteLine($"res = {res}");
    }
}
```

> * №4. Задача: Чему равен результат 7 / 2 и 7.0 / 2? Ответ: 3 (целочисленное деление) и 3.5 (деление с плавающей запятой).
```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 7 / 2;
        double b = 7.0 / 2;

        Console.WriteLine($"a = {a}");
        Console.WriteLine($"b = {b}");
    }
}
```

> * №5. Задача: Каков результат выражения -15 % 4 в C#? Ответ: -3 (знак остатка совпадает со знаком делимого).
```csharp
using System;

class Program
{
    static void Main()
    {
        int a = -15 % 4;

        Console.WriteLine($"a = {a}");
    }
}
```

> * №6. Задача: Что выведет выражение int x = 10; x = x++ + ++x;?

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 10;
        x = x++ + ++x;

        Console.WriteLine($"x = {x}");
    }
}
```
