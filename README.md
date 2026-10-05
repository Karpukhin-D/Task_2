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

> * №6. Задача: Что выведет выражение int x = 10; x = x++ + ++x;? Ответ: 22 (первое слагаемое 10, после него x становится 11, префиксный инкремент делает x = 12, итог 10+12=22).

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
        bool Foo()
        {
            Console.WriteLine("Foo вызван!");
            return true;
        }

        bool r = false & Foo();
        Console.WriteLine(r);
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
---

### 3.4. Побитовые операторы и сдвиги

---

> * №1. Задача: Чему равен результат 5 & 3 в двоичном и десятичном виде? Ответ: 0101 & 0011 = 0001 (десятичное 1).
```csharp
using System;

class Program
{
    static void Main()
    {
            int x = 5 & 3;

            Console.WriteLine($"{x}");
    }
}
```

> * №2. Задача: Чему равен результат 5 | 3? Ответ: 0101 | 0011 = 0111 (десятичное 7).

```csharp
using System;

class Program
{
    static void Main()
    {
            int x = 5 | 3;

            Console.WriteLine($"{x}");
    }
}
```

> * №3. Задача: Чему равен результат 5 ^ 3? Ответ: 0101 ^ 0011 = 0110 (десятичное 6).

```csharp
using System;

class Program
{
    static void Main()
    {
            int x = 5 ^ 3;

            Console.WriteLine($"{x}");
    }
}
```

> * №4. Задача: Вычислите ~0 для типа int. Ответ: -1 (все биты устанавливаются в 1, что в дополнительном коде равно -1).

```csharp
using System;

class Program
{
    static void Main()
    {
            int x = ~0;

            Console.WriteLine($"{x}");
    }
}
```

> * №5. Задача: Чему равно 1 << 4? Ответ: 16 

```csharp
using System;

class Program
{
    static void Main()
    {
            int x = 1 << 4;

            Console.WriteLine($"{x}");
    }
}
```

> * №6. Задача: Чему равно 40 >> 2? Ответ: 10

```csharp
using System;

class Program
{
    static void Main()
    {
            int x = 40 >> 2;

            Console.WriteLine($"{x}");
    }
}
```

> * №7. Задача: Как с помощью побитовой операции проверить, установлен ли третий бит числа n (маска 2^3=8)? 

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Введите число n: ");
        int n = Convert.ToInt32(Console.ReadLine());

        bool x = (n & 8) != 0;

        Console.WriteLine($"3-й бит установлен: {x}");
    }
}
```

> * №8. Задача: Как с помощью побитовой операции установить 2-й бит числа n в 1? Ответ: n = n | (1 << 2); (или n |= (1 << 2);).

```csharp
using System;

class Program
{
    static void Main()
    {
        int n = 5;
        n |= (1 << 2);

        Console.WriteLine(n);
    }
}
```

> * №9. Задача: Как сбросить (установить в 0) 4-й бит числа n? Ответ: n = n & ~(1 << 4); (или n &= ~(1 << 4);).

```csharp
using System;

class Program
{
    static void Main()
    {
        int n = 25;
        n = n & ~(1 << 4);

        Console.WriteLine($"{n}");
    }
}
```

> * №10. Задача: Каков результат выражения (-16) >> 2 для int? Ответ: -4 (арифметический сдвиг вправо сохраняет знаковый бит 1).

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = (-16) >> 2;

        Console.WriteLine($"{x}");
    }
}
```

---

### 3.5. Операторы присваивания

---

> * №1. Задача: Что делает оператор x += 5? Ответ: Эквивалентен x = x + 5 (с приведением типа при необходимости).

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 8;
        x += 5;

        Console.WriteLine($"{x}");
    }
}
```

> * №2. Задача: Каково значение a после выполнения: int a = 10; a *= 2 + 3;? Ответ: 50 (правая часть вычисляется полностью перед умножением: a = a * (2 + 3)).

```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 10;
        a *= 2 + 3;

        Console.WriteLine($"{a}");
    }
}
```

> * №3. Задача: Чему равен x после int x = 12; x >>= 2;? Ответ: 3.

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 12; 
        x >>= 2;

        Console.WriteLine($"{x}");
    }
}
```

> * №4. Задача: Что делает оператор x ??= y? Ответ: Присваивает переменной x значение y только в том случае, если x == null.

```csharp
using System;

class Program
{
    static void Main()
    {
        int? x = null;
        int y = 7;
        x = x ?? y;

        Console.WriteLine($"{x}");
    }
}
```

> * №5. Задача: Чему будет равна строка str после: string str = null; str ??= "default"; str ??= "custom"; Ответ: "default".

```csharp
using System;

class Program
{
    static void Main()
    {
        string str = null;
        str ??= "default";
        str ??= "custom";

        Console.WriteLine($"{str}");
    }
}
```

> * №6. Задача: Допустимо ли выражение byte b = 1; b += 2; без явного приведения? Ответ: Да, составные операторы присваивания содержат неявное сужающее приведение типа: b = (byte)(b + 2).

```csharp
using System;

class Program
{
    static void Main()
    {
        byte b = 1; 
        b += 2;

        Console.WriteLine($"{b}");
    }
}
```

> * №7. Задача: Чему равно значение c после int a = 5, b = 10, c = 0; c = a = b;? Ответ: 10 (присваивание ассоциативно справа налево).

```csharp
using System;

class Program
{
    static void Main()
    {
        int a = 5, b = 10, c = 0; 
        c = a = b;

        Console.WriteLine($"{c}");
    }
}
```

> * №8. Задача: Каково значение mask после: int mask = 1; mask <<= 3; mask |= 2;? Ответ: 10 (1 << 3 = 8, затем 8 | 2 = 10).

```csharp
using System;

class Program
{
    static void Main()
    {
        int mask = 1;
        mask <<= 3; 
        mask |= 2;

        Console.WriteLine($"{mask}");
    }
}
```

> * №9. Задача: Чему равно x после int x = 15; x %= 4;? Ответ: 3.

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 15;
        x %= 4;

        Console.WriteLine($"{x}");
    }
}
```



> * №10. Задача: Чему равно x после int x = 7; x ^= 7;? Ответ: 0 (любое число XOR само с собой дает 0).

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 7;
        x ^= 7;

        Console.WriteLine($"{x}");
    }
}
```
---

### 3.6. Тернарный и null-операторы

---

> * №1. Задача: Вычислите int score = 75; string res = score >= 60 ? "Pass" : "Fail";. Ответ: "Pass".

```csharp
using System;

class Program
{
    static void Main()
    {
        int score = 75; 
        string res = score >= 60 ? "Pass" : "Fail";

        Console.WriteLine($"{res}");
    }
}
```

> * №2. Задача: Чему равно int x = 5; int y = (x > 10) ? 100 : (x > 2) ? 50 : 0;? Ответ: 50.

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = 5; 
        int y = (x > 10) ? 100 : (x > 2) ? 50 : 0;

        Console.WriteLine($"{y}");
    }
}
```

> * №3. Задача: Какой тип имеет результат выражения true ? 10 : 15.5? Ответ: double.

```csharp
using System;

class Program
{
    static void Main()
    {
        double x = true ? 10 : 15.5;

        Console.WriteLine($"{x}");
    }
}
```

> * №4. Задача: Что выведет выражение string s = null; Console.WriteLine(s?.Length);? Ответ: Ничего / null (оператор ?. предотвращает NullReferenceException).

```csharp
using System;

class Program
{
    static void Main()
    {
        string s = null;
        
        Console.WriteLine(s?.Length);
    }
}
```

> * №5. Задача: Какой тип имеет результат выражения s?.Length для string s? Ответ: int? (Nullable<int>).

```csharp
using System;

class Program
{
    static void Main()
    {
        string s = null;
        int? x = s?.Length;

        Console.WriteLine($"{x}");
    }
}
```

> * №6. Задача: Вычислите: string name = null; string res = name ?? "Anonymous";. Ответ: "Anonymous".

```csharp
using System;

class Program
{
    static void Main()
    {
        string name = null; 
        string res = name ?? "Anonymous";

        Console.WriteLine($"{res}");
    }
}
```

> * №7. Задача: Вычислите: string a = null, b = "User", c = "Admin"; string res = a ?? b ?? c;. Ответ: "User".

```csharp
using System;

class Program
{
    static void Main()
    {
        string a = null, b = "User", c = "Admin"; 
        string res = a ?? b ?? c;

        Console.WriteLine($"{res}");
    }
}
```

> * №8. Задача: Что вернет выражение false ? (10 / 0) : 42? Ответ: 42 (второй операнд не вычисляется из-за ложного условия).

```csharp
using System;

class Program
{
    static void Main()
    {
        int zero = 0;
        int res = false ? (10 / zero) : 42;

        Console.WriteLine($"{res}");
    }
}
```

> * №9. Задача: Скомпилируется ли код var x = condition ? 10 : "text";? Ответ: Нет (в классическом C#), так как у типов int и string нет неявного взаимного приведения.

```csharp
using System;

class Program
{
    static void Main()
    {
        bool condition = true;
        var x = condition ? 10 : "text";

        Console.WriteLine($"{x}");
    }
}
```

> * №10. Задача: Чему равно int? count = null; int res = count?.GetHashCode() ?? -1;? Ответ: -1.

```csharp
using System;

class Program
{
    static void Main()
    {
        int? count = null; 
        int res = count?.GetHashCode() ?? -1;

        Console.WriteLine($"{res}");
    }
}
```
---

### 3.7. Операторы типов и приведения

---

> * №1. Задача: Что вернет выражение object obj = "Hello"; bool check = obj is string;? Ответ: true.

```csharp
using System;

class Program
{
    static void Main()
    {
        object obj = "Hello"; 
        bool check = obj is string;

        Console.WriteLine($"{check}");
    }
}
```

> * №2. Задача: Что вернет object obj = 123; string s = obj as string;? Ответ: null (оператор as возвращает null при невозможности безопасного приведения ссылочного типа).

```csharp
using System;

class Program
{
    static void Main()
    {
        object obj = 123; 
        string s = obj as string;

        Console.WriteLine($"{s}");
    }
}
```

> * №3. Задача: Что произойдет при явном приведении object obj = 123; string s = (string)obj;? Ответ: Выбросится исключение System.InvalidCastException.

```csharp
using System;

class Program
{
    static void Main()
    {
        object obj = 123;
        string s = (string)obj;

        Console.WriteLine($"{s}");
    }
}
```

> * №4. Задача: Что вернет typeof(int) == typeof(Int32)? Ответ: true (псевдоним языка ссылается на один и тот же тип CLR).

```csharp
using System;

class Program
{
    static void Main()
    {
        bool res = typeof(int) == typeof(Int32);

        Console.WriteLine($"{res}");
    }
}
```

> * №5. Задача: Чему равен результат sizeof(long) в байтах? Ответ: 8.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine($"sizeof(long) = {sizeof(long)} байт");
    }
}
```

> * №6. Задача: Что вернет null is string? Ответ: false (шаблон is для null всегда возвращает false, кроме шаблона is null).

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine($"{null is string}");
    }
}
```

> * №7. Задача: Что вернет выражение object x = null; bool b = x is null;? Ответ: true.

```csharp
using System;

class Program
{
    static void Main()
    {
        object x = null;
        bool b = x is null;

        Console.WriteLine($"{b}");
    }
}
```

> * №8. Задача: Каков результат (int)3.99? Ответ: 3 (дробная часть отсекается без округления).

```csharp
using System;

class Program
{
    static void Main()
    {
        int x = (int)3.99;

        Console.WriteLine($"{x}");
    }
}
```

> * №9. Задача: Каков результат pattern matching: object o = 42; if (o is int val && val > 40) { ... } Будет ли выполнено тело блока? Ответ: Да, val получит значение 42, условие val > 40 истинно.

```csharp
using System;

class Program
{
    static void Main()
    {
        object o = 42;
        if (o is int val && val > 40);

        Console.WriteLine($"{o}");
    }
}
```

> * №10. Задача: Что вернет выражение default(int) и default(string)? Ответ: 0 и null.

```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine($"{default(int)}, {default(string) ?? "null"}");
    }
}
```

---

### 4. 35 сложносоставных заданий на логические выражения

---

> * №1. (5 > 3) && !(10 <= 2) || (4 == 5)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (5 > 3) && !(10 <= 2) || (4 == 5);

        Console.WriteLine($"№1: {x}");
    }
}
```

> * №2. !(true && false) ^ (true || false && false)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !(true && false) ^ (true || false && false);

        Console.WriteLine($"№2: {x}");
    }
}
```

> * №3. (10 & 6) == 2 && (10 | 6) == 14

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (10 & 6) == 2 && (10 | 6) == 14;

        Console.WriteLine($"№3: {x}");
    }
}
```

> * №4. (15 >> 1 == 7) && (7 << 2 == 28)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (15 >> 1 == 7) && (7 << 2 == 28);

        Console.WriteLine($"№4: {x}");
    }
}
```

> * №5. (8 > 5) && (3 + 2 * 4 == 11) && !(false || !true)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (8 > 5) && (3 + 2 * 4 == 11) && !(false || !true);

        Console.WriteLine($"№5: {x}");
    }
}
```

> * №6. (true || false) && (false || true) ^ (true && !false)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (true || false) && (false || true) ^ (true && !false);

        Console.WriteLine($"№6: {x}");
    }
}
```

> * №7. (100 / 10 == 10) && (100 % 30 == 10) && !(5 - 5 != 0)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (100 / 10 == 10) && (100 % 30 == 10) && !(5 - 5 != 0);

        Console.WriteLine($"№7: {x}");
    }
}
```

> * №8. (4 ^ 4) == 0 && (4 ^ 0) == 4 && (0 ^ 0) == 0

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (4 ^ 4) == 0 && (4 ^ 0) == 4 && (0 ^ 0) == 0;

        Console.WriteLine($"№8: {x}");
    }
}
```

> * №9. !(5 != 5) && ((3 >= 3) || (10 / 0 == 1))

```csharp
using System;

class Program
{
    static void Main()
    {
        int z = 0;
        bool x = !(5 != 5) && ((3 >= 3) || (10 / z == 1));

        Console.WriteLine($"№9: {x}");
    }
}
```

> * №10. (false && (10 / 0 == 1)) || (true && (20 > 15))

```csharp
using System;

class Program
{
    static void Main()
    {
        int z = 0;
        bool x = (false && (10 / z == 1)) || (true && (20 > 15));

        Console.WriteLine($"№10: {x}");
    }
}
```

> * №11. (12 & 10) > 5 || (12 | 10) < 15 && !(3 == 3)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (12 & 10) > 5 || (12 | 10) < 15 && !(3 == 3);

        Console.WriteLine($"№11: {x}");
    }
}
```

> * №12. ((20 >> 2) == 5) ^ ((5 << 1) == 11)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((20 >> 2) == 5) ^ ((5 << 1) == 11);

        Console.WriteLine($"№12: {x}");
    }
}
```

> * №13. !(!(true || false) && (true && !false))

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !(!(true || false) && (true && !false));

        Console.WriteLine($"№13: {x}");
    }
}
```

> * №14. (7 > 2 ? 10 : 20) == 10 && (3 < 1 ? 5 : 15) == 15

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (7 > 2 ? 10 : 20) == 10 && (3 < 1 ? 5 : 15) == 15;

        Console.WriteLine($"№14: {x}");
    }
}
```

> * №15. (5 & 1) == 1 && (6 & 1) == 0 && (7 & 1) == 1 (проверка на нечетность)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (5 & 1) == 1 && (6 & 1) == 0 && (7 & 1) == 1;

        Console.WriteLine($"№15: {x}");
    }
}
```

> * №16. ((10 > 5 ? true : false) ^ (3 > 8 ? true : false)) && !false

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((10 > 5 ? true : false) ^ (3 > 8 ? true : false)) && !false;

        Console.WriteLine($"№16: {x}");
    }
}
```

> * №17. !( (5 > 2 && 10 > 20) || (3 == 3 && 4 <= 4) )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !((5 > 2 && 10 > 20) || (3 == 3 && 4 <= 4));

        Console.WriteLine($"№17: {x}");
    }
}
```

> * №18. ( (1 << 3) == 8 ) && ( (16 >> 4) == 1 ) && ( (2 << 2) == 8 )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((1 << 3) == 8) && ((16 >> 4) == 1) && ((2 << 2) == 8);

        Console.WriteLine($"№18: {x}");
    }
}
```

> * №19. ( (10 & 7) == 2 ) || ( (10 | 7) == 15 ) ^ !(4 > 1)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((10 & 7) == 2) || ((10 | 7) == 15) ^ !(4 > 1);

        Console.WriteLine($"№19: {x}");
    }
}
```

> * №20. false || true && false || true && !false

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = false || true && false || true && !false;

        Console.WriteLine($"№20: {x}");
    }
}
```

> * №21. (25 % 4 == 1) && (17 / 3 == 5) && (17 % 3 == 2)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (25 % 4 == 1) && (17 / 3 == 5) && (17 % 3 == 2);

        Console.WriteLine($"№21: {x}");
    }
}
```

> * №22. ( (5 ^ 3 ^ 3) == 5 ) && ( (10 ^ 0) == 10 )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((5 ^ 3 ^ 3) == 5) && ((10 ^ 0) == 10);

        Console.WriteLine($"№22: {x}");
    }
}
```

> * №23. (true ? (false ? 1 : 2) : (true ? 3 : 4)) == 2

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (true ? (false ? 1 : 2) : (true ? 3 : 4)) == 2;

        Console.WriteLine($"№23: {x}");
    }
}
```

> * №24. !(true && !(false || !false))

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !(true && !(false || !false));

        Console.WriteLine($"№24: {x}");
    }
}
```

> * №25. ( (~0 == -1) && (~(-1) == 0) )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((~0 == -1) && (~(-1) == 0));

        Console.WriteLine($"№25: {x}");
    }
}
```

> * №26. ( (8 & 4) == 0 ) && ( (8 | 4) == 12 ) && ( (8 ^ 4) == 12 )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((8 & 4) == 0) && ((8 | 4) == 12) && ((8 ^ 4) == 12);

        Console.WriteLine($"№26: {x}");
    }
}
```

> * №27. !(10 >= 10) || (5 < 3) && (2 == 2) || !(false)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !(10 >= 10) || (5 < 3) && (2 == 2) || !(false);

        Console.WriteLine($"№27: {x}");
    }
}
```

> * №28. ( (15 & ~1) == 14 ) && ( (14 | 1) == 15 )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((15 & ~1) == 14) && ((14 | 1) == 15);

        Console.WriteLine($"№28: {x}");
    }
}
```

> * №29. ( (true || false) ? (false && true ? 10 : 20) : 30 ) == 20

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((true || false) ? (false && true ? 10 : 20) : 30) == 20;

        Console.WriteLine($"№29: {x}");
    }
}
```

> * №30. ( (10 > 2) && (5 < 9) ) ^ ( !(4 >= 5) && (6 != 7) )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((10 > 2) && (5 < 9)) ^ (!(4 >= 5) && (6 != 7));

        Console.WriteLine($"№30: {x}");
    }
}
```

> * №31. (7 & 3 & 1) == 1 && (7 | 3 | 1) == 7

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = (7 & 3 & 1) == 1 && (7 | 3 | 1) == 7;

        Console.WriteLine($"№31: {x}");
    }
}
```

> * №32. ( (10 > 5 && 3 < 1) || (8 == 8 && !(5 > 10)) ) && (4 + 4 == 8)

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((10 > 5 && 3 < 1) || (8 == 8 && !(5 > 10))) && (4 + 4 == 8);

        Console.WriteLine($"№32: {x}");
    }
}
```

> * №33. !( (!(true && false) || !(true || false)) && !false )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = !((!(true && false) || !(true || false)) && !false);

        Console.WriteLine($"№33: {x}");
    }
}
```

> * №34. ( (32 >> 3 == 4) && (4 << 3 == 32) ) ^ ( (15 & 7) == 7 && (15 | 7) == 15 )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((32 >> 3 == 4) && (4 << 3 == 32)) ^ ((15 & 7) == 7 && (15 | 7) == 15);

        Console.WriteLine($"№34: {x}");
    }
}
```

> * №35. ( (5 > 3 ? (2 > 1 ? true : false) : false) && !( (10 > 20) || (30 < 15) ) )

```csharp
using System;

class Program
{
    static void Main()
    {
        bool x = ((5 > 3 ? (2 > 1 ? true : false) : false) && !((10 > 20) || (30 < 15)));

        Console.WriteLine($"№35: {x}");
    }
}
```
