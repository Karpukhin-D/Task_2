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
---

### 3.2. Операторы сравнения и равенства

---

> * №1. Задача: Каков результат 5 > 3 и 5 >= 5? Ответ: true, true.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = 5 > 3;
        bool b = 5 >= 5;

        Console.WriteLine($"a = {a}");
        Console.WriteLine($"b = {b}");
    }
}
```

> * №2. Задача: Чему равно "hello" == "hello" в C# и почему? Ответ: true, так как для типа string оператор == перегружен для посимвольного сравнения значений.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = "hello" == "hello";

        Console.WriteLine($"{x}");
    }
}
```

> * №3. Задача: Чему равно выражение double.NaN == double.NaN? Ответ: false (по стандарту IEEE 754 NaN не равен ничему, даже самому себе).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = double.NaN == double.NaN;

        Console.WriteLine($"{x}");
    }
}
```

> * №4. Задача: Каков результат выражения object a = new int[] { 1 }; object b = new int[] { 1 }; bool r = a == b;? Ответ: false (сравниваются ссылки на два разных объекта в куче).

```csharp
using System;

class Program
{
    static void Main()
    {
        object a = new int[] { 1 };
        object b = new int[] { 1 }; 
        bool r = a == b;

        Console.WriteLine($"r = {r}");
    }
}
```

> * №5. Задача: Чему равно 10 != 10.0? Ответ: false (целое число 10 неявно приводится к 10.0, значения равны).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = 10 != 10.0;

        Console.WriteLine($"a = {a}");
    }
}
```

> * №6. Задача: Что вернет null == null? Ответ: true.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = null == null;

        Console.WriteLine($"a = {a}");
    }
}
```

> * №7. Задача: Каков результат выражения (3 < 5) == (10 >= 20)? Ответ: false (true == false дает false).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = (3 < 5) == (10 >= 20);

        Console.WriteLine($"a = {a}");
    }
}
```

> * №8. Задача: Вычислите bool res = 4 <= 4 && 5 > 2;. Ответ: true.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool res = 4 <= 4 && 5 > 2;

        Console.WriteLine($"res = {res}");
    }
}
```

> * №9. Задача: Что вернет выражение char c = 'b'; bool res = c > 'a';? Ответ: true (символы сравниваются по их числовым кодам Unicode: 98 > 97).

```csharp
using System;

class Program
{
    static void Main()
    {
        char c = 'b';
        bool res = c > 'a';

        Console.WriteLine($"res = {res}");
    }
}
```

> * №10. Задача: Сравните результат bool r = -0.0 == 0.0;. Ответ: true (ноль со знаком равен обычному нулю).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool r = -0.0 == 0.0;

        Console.WriteLine($"r = {r}");
    }
}
```
---
### 3.3. Логические операторы
---

> * №1. Задача: Вычислите: !true || false && true. Ответ: false (приоритет: ! -> && -> ||: false || false дает false).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = !true || false && true;

        Console.WriteLine($"a = {a}");
    }
}
```

> * №2. Задача: Будет ли вызван метод Foo() в false && Foo()? Ответ: Нет, благодаря короткому замыканию оператора &&.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = false && Foo();

        Console.WriteLine($"a = {a}");
    }
}
```

> * №3. Задача: Будет ли вызван метод Foo() в false & Foo()? Ответ: Да, побитовое/строгое логическое & вычисляет оба операнда.

```csharp
using System;

class Program
{
    static void Main()
    {
....
    }
}
```

> * №4. Задача: Вычислите результат: true ^ false ^ true. Ответ: false (true ^ false = true, затем true ^ true = false).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = true ^ false ^ true;

        Console.WriteLine($"a = {a}");
    }
}
```

> * №5. Задача: Что вернет выражение !(5 > 2 || 3 < 1)? Ответ: false (5 > 2 истинно, внутри скобок true, отрицание дает false).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = !(5 > 2 || 3 < 1);

        Console.WriteLine($"a = {a}");
    }
}
```

> * №6. Задача: Дано: bool a = true, b = false;. Чему равно a && !b || b && !a? Ответ: true (true && true || false && false -> true || false -> true).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = true, b = false;
        bool c = a && !b || b && !a;

        Console.WriteLine($"c = {c}");
    }
}
```

> * №7. Задача: Каков результат true || (x / 0 == 1) при любом целом x? Ответ: true (деление на ноль не произойдет из-за короткого замыкания ||).

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 10;
        bool a = true || (x / 0 == 1);

        Console.WriteLine($"a = {a}");
    }
}
```

> * №8. Задача: Каков результат false & (10 / 0 == 1)? Ответ: Выбросится исключение DivideByZeroException, так как & обязательно вычисляет правый операнд.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool a = false & (10 / 0 == 1);

        Console.WriteLine($"a = {a}");
    }
}
```

> * №9. Задача: Чему эквивалентно выражение !(A && B) по закону де Моргана? Ответ: !A || !B.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool A = true, B = false;
        bool DeMorgan = !(A && B);
        bool DeMorganEquivalent = !A || !B;

        Console.WriteLine($"{DeMorgan}, {DeMorganEquivalent}");
    }
}
```

> * №10. Задача: Чему эквивалентно выражение !(A || B) по закону де Моргана? Ответ: !A && !B.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool A = true, B = false;
        bool DeMorgan = !(A || B);
        bool DeMorganEquivalent = !A && !B;

        Console.WriteLine($"{DeMorgan}, {DeMorganEquivalent}");
    }
}
```
