# Tamrin.5
using System;

class Program
{
    // متد محاسبه محیط مثلث
    static double CalculatePerimeter(double a, double b, double c)
    {
        return a + b + c;
    }

    // متد محاسبه مساحت مثلث
    static double CalculateArea(double a, double b, double c)
    {
        double s = (a + b + c) / 2;  // نیم‌محیط مثلث
        return Math.Sqrt(s * (s - a) * (s - b) * (s - c)); // فرمول هرفن
    }

    static void Main()
    {
        // ورودی سه ضلع مثلث از کاربر
        Console.Write("لطفاً ضلع اول مثلث (a) را وارد کنید: ");
        double a = double.Parse(Console.ReadLine());
        
        Console.Write("لطفاً ضلع دوم مثلث (b) را وارد کنید: ");
        double b = double.Parse(Console.ReadLine());
        
        Console.Write("لطفاً ضلع سوم مثلث (c) را وارد کنید: ");
        double c = double.Parse(Console.ReadLine());

        // بررسی صحت مثلث بودن
        if (a + b > c && a + c > b && b + c > a)
        {
            // محاسبه محیط و مساحت مثلث
            double perimeter = CalculatePerimeter(a, b, c);
            double area = CalculateArea(a, b, c);

            // نمایش نتایج
            Console.WriteLine("\nمحیط مثلث: " + perimeter);
            Console.WriteLine("مساحت مثلث: " + area);
        }
        else
        {
            Console.WriteLine("این اعداد نمی‌توانند یک مثلث بسازند.");
        }
    }
}
