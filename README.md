# Lesson_5_HomeWork
## Задача 34: Задайте массив заполненный случайными положительными трёхзначными числами. Напишите программу, которая покажет количество чётных чисел в массиве.
[345, 897, 568, 234] -> 2
```
int[] Array = CreateArray(10, 100, 999);
PrintArray(Array);
int Count = 0;
for (int i = 0; i < Array.Length; i++)
{
    if (Array[i] % 2 == 0)
        Count++;
}
Console.Write($"\n {Count}");
```

```
int[] CreateArray(int size, int min, int max)
{
    int[] _Array = new int[size];
    for (int i = 0; i < size; i++)
        _Array[i] = new Random().Next(min, max);
    return _Array;
}

void PrintArray(int[] _Array)
{
    foreach (var item in _Array)
        Console.Write($"{item} ");
}
```
## Задача 36: Задайте одномерный массив, заполненный случайными числами. Найдите сумму элементов, стоящих на нечётных позициях.
[3, 7, 23, 12]-> 19
[-4, -6, 89, 6]-> 0

```
int[] Array = CreateArray(10, 0, 10);
PrintArray(Array);
int Sum = 0;
for (int i = 1; i < Array.Length; i++)
    if (i % 2 != 0)
    {
        Sum = Sum + Array[i];
    }
Console.Write($"\n {Sum}");
```

## Задача 38: Задайте массив вещественных чисел. Найдите разницу между максимальным и минимальным элементов массива.
[3 7 22 2 78]-> 76
### в одном цикле
```
int[] Array = CreateArray(10, 1, 10);
PrintArray(Array);

int Max = Array[1];
int Min = Array[0];
if (Max < Min)
    Max = Array[0];
Min = Array[1];
for (int i = 2; i < Array.Length; i++)
    if (Array[i] > Max)
    {
        Max = Array[i];
    }
    else if (Array[i] < Min)
    {
        Min = Array[i];
    }
Console.Write($"\n Разницу между максимальным и минимальным элементов массива = {Max - Min}");
```

### в Двух циклах
```
int Max = Array[0];
for (int i = 1; i < Array.Length; i++)
    if (Array[i] > Max)
    {
        Max = Array[i];
    }
int Min = Array[0];
for (int i = 0; i < Array.Length; i++)
    if (Array[i] < Min)
    {
        Min = Array[i];
    }

Console.Write($"\n Разницу между максимальным и минимальным элементов массива = {Max - Min}");
```