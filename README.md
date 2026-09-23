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

> * №7. Задача: Что произойдет при выполнении int max = int.MaxValue; int res = checked(max + 1);? Ответ: Выбросится исключение System.OverflowException.

```csharp
using System;

class Program
{
    static void Main()
    {
        int max = int.MaxValue; 
        int res = checked(max + 1);

        Console.WriteLine($"res = {res}");
    }
}
```

> * №8. Задача: Что произойдет при int max = int.MaxValue; int res = unchecked(max + 1);? Ответ: res = int.MinValue (произойдет переполнение без ошибки).

```csharp
using System;

class Program
{
    static void Main()
    {
        int max = int.MaxValue; 
        int res = unchecked(max + 1);

        Console.WriteLine($"res = {res}");
    }
}
```

> * №9. Задача: Чему равен результат деления 1.0 / 0.0 и 0.0 / 0.0? Ответ: double.PositiveInfinity (Infinity) и double.NaN.

```csharp
using System;

class Program
{
    static void Main()
    {
        double a = 1.0 / 0.0; 
        double b = 0.0 / 0.0;

        Console.WriteLine($"a = {a}");
        Console.WriteLine($"b = {b}");
    }
}
```

> * №10. Задача: Вычислите: int a = 8; int b = 3; int c = a - b * 2 + a / b;. Ответ: 8 - 6 + 2 = 4.

```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 8; 
        int b = 3;
        int c = a - b * 2 + a / b;

        Console.WriteLine($"c = {c}");
    }
}
```

