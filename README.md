```C#
using System;

double maxY = double.MinValue; // начальное значение для поиска максимуму функции y
double minY = double.MaxValue; // начальное значение для поиска минимума функции y
double opposite = 0;
double y1 = 0;
int point = 0;

Console.WriteLine("введите точку а");
double a = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("введите точку b");
double b = Convert.ToInt32(Console.ReadLine());

while (true)
    if (b > a)
    { break; }

    else
    {
        Console.WriteLine("b не может быть меньше a. попробуйте еще раз");
        b = Convert.ToDouble(Console.ReadLine());
    }

Console.WriteLine("введите шаг h");
double h = Convert.ToDouble(Console.ReadLine());
while (true)
    if (h != 0)
    { break; }

    else
    {
        Console.WriteLine("шаг не должен равнять нулю. попробуйте еще раз");
        h = Convert.ToDouble(Console.ReadLine());
    }



for (double x = a; x <= b; x += h)
{
    double y = y = Math.Round(Math.Cos(x * x) + (Math.Sin(x) * Math.Sin(x)), 2);
    Console.WriteLine($"x = {x}, y = {y}");

    { point++; } // Увеличение счетчика точек

    if (y > maxY) maxY = y;
    if (y < minY) minY = y;

    {
        if ((y1 < 0 && y > 0) || (y1 > 0 && y < 0))
        { opposite++; } // Если знак изменился, увеличиваем счетчик изменений знака
        y1 = y;
    }

}


Console.WriteLine($"Знаков изменено: {opposite}");
Console.WriteLine($"Количество точек: {point}");
Console.WriteLine($"Максимальное значение функции: {maxY}");
Console.WriteLine($"Минимальное значение функции: {minY}"); 




```
