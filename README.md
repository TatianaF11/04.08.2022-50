{
    //Задача 50. Напишите программу, которая на вход принимает позиции элемента в двумерном массиве,
    //и возвращает значение этого элемента или же указание, что такого элемента нет.
    //Например, задан массив:
    //1 4 7 2
    //5 9 2 3
    //8 4 2 4
    //17 -> такого числа в массиве нет
    Console.WriteLine("Введите количество строк");
    int m = Convert.ToInt32(Console.ReadLine());
    Console.WriteLine("Введите количество столбцов");
    int n = Convert.ToInt32(Console.ReadLine());
    Console.WriteLine("Введите элемент");
    int element = Convert.ToInt32(Console.ReadLine());
        
    int[,] Array = new int[m,n];
    CreateIntArray(Array);
    PrintIntArray(Array); 
    ElementInArray(Array, element);
}

int[,] CreateIntArray(int[,] arr)
{
    Random rand = new Random();
    int m = arr.GetLength(0);
    int n = arr.GetLength(1);
    for (int i = 0; i <m; i++)
    {
        for (int j = 0; j < n; j++)
        {
            arr[i,j] = rand.Next(1,10);
        }
    }
    return arr;
}

int[,] PrintIntArray(int[,] arr)
{
    int m = arr.GetLength(0);
    int n = arr.GetLength(1);
    for (int i = 0; i < m; i++)
    {
        for (int j = 0; j < n; j++)
        {
            Console.Write($"{arr[i,j]} ");
        }
        Console.WriteLine();
    }
    return arr;
}

void ElementInArray(int[,] arr, int element)
{
    bool flag = false;
    int m = arr.GetLength(0);
    int n = arr.GetLength(1);
    for (int i = 0; i < m; i++)
    {
        for (int j = 0; j <n; j++)
        {
            if (arr[i,j] == element)
            {
                flag = true;
                break;
            }
        }       
    }

    if (flag == true)
    {
        Console.WriteLine($"Элемент - {element}, есть в массиве ");
    }
    else {Console.WriteLine("Такого элемента нет в массиве");}  
}
//Zadacha50();
