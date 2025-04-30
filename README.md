# nekit

using System;

using System.Collections.Generic;

using System.Linq;

using System.Text;

using System.Threading.Tasks;

namespace s_massivom

{

    internal class Program
    
    {
    
        static void Main()
        
        {
        
                Console.Write("сколько элементов в массивах: ");
                
                double x = Convert.ToDouble(Console.ReadLine());
                
                while (x < 0 && x - Convert.ToInt32(x) != 0)
                
                {
                
                    Console.Write("массив не может быть отрицательным и должно быть целым числом. повторите ввод: ");
                    
                    x = Convert.ToDouble(Console.ReadLine());
                    
                }
                
                massive massive = new massive(Convert.ToInt32(x));
                
                massive.slozhenie();
                
                massive.vichitanie();
                
                
                massive.umnozhenie();
                
                massive.delenie();
                
                massive.vivodchisla();
                
                Console.ReadKey();
        }
    }

    class massive
    {
        public double[] arr1;
        public double[] arr2;
        public massive(int array)
        {
            Random random = new Random();
            arr1 = new double[array];
            arr2 = new double[array];
            Console.WriteLine("1 массив:");
            for (int i = 0; i < arr1.Length; i++)
            {
                arr1[i] = random.Next(0, 11);
                Console.Write(arr1[i] + " ");
            }
            Console.WriteLine();
            Console.WriteLine();

            Console.WriteLine("2 массив:");
            for (int i = 0; i < arr2.Length; i++)
            {
                arr2[i] = random.Next(0, 11);
                Console.Write(arr2[i] + " ");
            }
            Console.WriteLine();
            Console.WriteLine();
        }

        public void slozhenie()
        {
            Console.WriteLine("поэлементное сложение: ");
            for (int i = 0; i < arr1.Length; i++)
            {
                Console.Write($"{arr1[i] + arr2[i]} ");
            }
            Console.WriteLine();
            Console.WriteLine();
        }
        public void vichitanie()
        {
            Console.WriteLine("поэлементное вычитание: ");
            for (int i = 0; i < arr1.Length; i++)
            {
                Console.Write((arr1[i] - arr2[i]) + " ");
            }
            Console.WriteLine();
            Console.WriteLine();
        }

        public void umnozhenie()
        {
            double a = text("умножение");
            for (int i = 0; i < arr1.Length; i++)
            {
                Console.Write((arr1[i] * a) + " ");
            }
            Console.WriteLine();
            Console.WriteLine();
        }

        public void delenie()
        {
            double a = text("деление");
            while (a == 0)
            {
                Console.Write("делить на 0 нельзя. повторите ввод: ");
                a = Convert.ToInt32(Console.ReadLine());
            }
            for (int i = 0; i < arr1.Length; i++)
            {
                Console.Write((arr1[i] / a) + " ");
            }
            Console.WriteLine();
            Console.WriteLine();
        }

        public void vivodchisla()
        {
            double a = text("вывод элемента массива");
            Console.WriteLine("элемент под номером " + a + " равен " + arr1[Convert.ToInt32(a) - 1]);
        }

        private double text(string nazvanieopracii)
        {
            Console.Write($"введите число для операции {nazvanieopracii}: ");
            Console.WriteLine();
            double a = Convert.ToDouble(Console.ReadLine());
            while (a == 0 && nazvanieopracii == "деление")
            {
                Console.Write("нельзя делить на 0, повторите ввод: ");
                a = Convert.ToDouble(Console.ReadLine());
            }
            while (a - Convert.ToInt32(a) != 0 && nazvanieopracii == "вывод элемента массива" && a > 0 && a < arr1.Length)
            {
                Console.Write("элемент массива должен быть целым числом и быть в границах массива повторите ввод: ");
                a = Convert.ToDouble(Console.ReadLine());
            }
            return a;
        }
    }
}
