using System;
using System.Collections.Generic;
using System.Linq;
using System.Security.Cryptography;
using System.Text;
using System.Threading.Tasks;

namespace project_the_matrix
{
    class Program
    {
        static void Main(string[] args)
        {
            string secim;
            Console.Write("for group A,B,C enter 1, for group D enter 2: ");
            secim = Console.ReadLine();
            if (secim == "1")
            {
                double a1, a2, a3, b1, b2, b3, c1, c2, c3;
                Console.WriteLine("|  a1  b1  c1  |\n|  a2  b2  c2  |\n|  a3  b3  c3  |");
                Console.WriteLine("enter the matrix elements");
                Console.Write("a1: ");
                a1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("a2: ");
                a2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("a3: ");
                a3 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b1: ");
                b1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b2: ");
                b2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b3: ");
                b3 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c1: ");
                c1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c2: ");
                c2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c3: ");
                c3 = Convert.ToDouble(Console.ReadLine());
                Console.WriteLine("***********");
                Console.WriteLine("entered matrix: ");
                Console.WriteLine("| {0}    {1}    {2}  |", a1, b1, c1);
                Console.WriteLine("| {0}    {1}    {2}  |", a2, b2, c2);
                Console.Write("| {0}    {1}    {2}  |", a3, b3, c3);
                Console.ReadLine();
                double r1 = a1 + b1 + c1;
                double r2 = a2 + b2 + c2;
                double r3 = a3 + b3 + c3;
                Console.WriteLine("***********");
                Console.WriteLine("sum of row1: " + r1);
                Console.WriteLine("sum of row2: " + r2);
                Console.WriteLine("sum of row3: " + r3);
                Console.ReadLine();
                double co1 = a1 + a2 + a3;
                double co2 = b1 + b2 + b3;
                double co3 = c1 + c2 + c3;
                Console.WriteLine("***********");
                Console.WriteLine("sum of column1: " + co1);
                Console.WriteLine("sum of column2: " + co2);
                Console.Write("sum of column3: " + co3);
                Console.ReadLine();
                double pr = a1 + b2 + c3;
                Console.WriteLine("***********");
                Console.Write("sum of the primary diagonal: " + pr);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("transpose of the matrix: ");
                Console.WriteLine("| {0}    {1}    {2}  |", a1, a2, a3);
                Console.WriteLine("| {0}    {1}    {2}  |", b1, b2, b3);
                Console.Write("| {0}    {1}    {2}  |", c1, c2, c3);
                Console.ReadLine();
                double det = a1 * b2 * c3 + a2 * b3 * c1 + a3 * b1 * c2 - (a3 * b2 * c1 + a1 * b3 * c2 + a2 * b1 * c3);
                Console.WriteLine("***********");
                Console.Write("determinant of the matrix: " + det);
                Console.ReadLine();
                Console.WriteLine("***********");
                if (a1 == 1 && a2 == 0 && a3 == 0 && b1 == 0 && b2 == 1 && b3 == 0 && c1 == 0 && c2 == 0 && c3 == 1)
                    Console.WriteLine("identity matrix : yes");
                else
                    Console.WriteLine("identity matrix : no");
                if (a1 == b2 && a1 == c3 && a2 == 0 && a3 == 0 && b1 == 0 && b3 == 0 && c1 == 0 && c2 == 0)
                    Console.WriteLine("scalar matrix : yes");
                else
                    Console.WriteLine("scalar matrix : no");
                if (a1 != 0 && a2 == 0 && a3 == 0 && b1 == 0 && b2 != 0 && b3 == 0 && c1 == 0 && c2 == 0 && c3 != 0)
                    Console.WriteLine("Diagonal matrix : yes");
                else
                    Console.WriteLine("Diagonal matrix : no");
                if (a1 == 0 || a1 == 1 && a2 == 0 || a2 == 1 && a3 == 0 || a3 == 1 && b1 == 0 || b1 == 1 && b2 == 0 || b2 == 1 && b3 == 0 || b3 == 1 && c1 == 0 || c1 == 1 && c2 == 0 || c2 == 1 && c3 == 0 || c3 == 1)
                    Console.WriteLine("Zero-one matrix : yes");
                else
                    Console.WriteLine("Zero-one matrix : no");
                if (a2 == b1 && a3 == c1 && b3 == c2)
                    Console.WriteLine("Symmetric matrix : yes");
                else
                    Console.WriteLine("Symmetric matrix : no");
                if (r1 == 1 && r2 == 1 && r3 == 1 && co1 == 1 && co2 == 1 && co3 == 1)
                    Console.WriteLine("Permutation matrix : yes");
                else
                    Console.WriteLine("Permutation matrix : no");
                Console.ReadLine();
                Console.WriteLine("***********");
                double min1 = Math.Min(Math.Min(a1, b1), c1);
                double min2 = Math.Min(Math.Min(a2, b2), c2);
                double min3 = Math.Min(Math.Min(a3, b3), c3);
                Console.WriteLine("Minimum values of each row: {0}   {1}   {2}", min1, min2, min3);
                Console.ReadLine();
                double max1 = Math.Max(Math.Max(a1, a2), a3);
                double max2 = Math.Max(Math.Max(b1, b2), b3);
                double max3 = Math.Max(Math.Max(c1, c2), c3);
                Console.WriteLine("Maximum values of each column: {0}   {1}   {2}", max1, max2, max3);
                Console.ReadLine();
                double maxmin = Math.Max(Math.Max(min1, min2), min3);
                Console.WriteLine("Maximum of minimum values of each row: " + maxmin);
                Console.ReadLine();
                double minmax = Math.Min(Math.Min(max1, max2), max3);
                Console.WriteLine("Minimum of maximum values of each column: " + minmax);
                Console.ReadLine();
                if (maxmin > minmax)
                    Console.WriteLine("Compare maxmin to minmax: maxmin>minmax");
                else if (maxmin < minmax)
                    Console.WriteLine("Compare maxmin to minmax: maxmin<minmax");
                else
                    Console.WriteLine("Compare maxmin to minmax: maxmin=minmax");
                Console.ReadLine();
            }
            else if (secim == "2")
            {
                double a1, a2, a3, b1, b2, b3, c1, c2, c3, d1, d2, d3;
                Console.WriteLine("***********");
                Console.WriteLine("|  a1  b1  c1  d1  |\n|  a2  b2  c2  d2  |\n|  a3  b3  c3  d3  |");
                Console.WriteLine("***********");
                Console.WriteLine("Enter the matrix for Gauss Elimination Method");
                Console.Write("a1: ");
                a1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("a2: ");
                a2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("a3: ");
                a3 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b1: ");
                b1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b2: ");
                b2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("b3: ");
                b3 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c1: ");
                c1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c2: ");
                c2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("c3: ");
                c3 = Convert.ToDouble(Console.ReadLine());
                Console.Write("d1: ");
                d1 = Convert.ToDouble(Console.ReadLine());
                Console.Write("d2: ");
                d2 = Convert.ToDouble(Console.ReadLine());
                Console.Write("d3: ");
                d3 = Convert.ToDouble(Console.ReadLine());
                Console.WriteLine("***********");
                Console.WriteLine("entered matrix: ");
                Console.WriteLine("| {0}    {1}    {2}    {3}  |", a1, b1, c1, d1);
                Console.WriteLine("| {0}    {1}    {2}    {3}  |", a2, b2, c2, d2);
                Console.Write("| {0}    {1}    {2}    {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("Conversion of the matrix: ");
                Console.WriteLine("step 1.");
                b1 = b1 / a1;
                c1 = c1 / a1;
                d1 = d1 / a1;
                a1 = 1;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |",a1,b1,c1,d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("Step 2. ");
                b2 -= b1 * a2;
                c2 -= c1 * a2;
                d2 -= d1 * a2;
                a2 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 3.");
                b3 -= b1 * a3;
                c3 -= c1 * a3;
                d3 -= d1 * a3;
                a3 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 4.");
                c2 /= b2;
                d2 /= b2;
                b2 = 1;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 5.");
                c1 -= c2 * b1;
                d1 -= d2 * b1;
                b1 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 6.");
                c3 -= c2 * b3;
                d3 -= d2 * b3;
                b3 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 7.");
                d3 /= c3;
                c3 /= c3;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 8.");
                d1 -= c1 * d3;
                c1 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("step 9.");
                d2 -= c2 * d3;
                c2 = 0;
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a1, b1, c1, d1);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a2, b2, c2, d2);
                Console.WriteLine("|  {0}   {1}   {2}   {3}  |", a3, b3, c3, d3);
                Console.ReadLine();
                Console.WriteLine("***********");
                Console.WriteLine("The value of unknowns (x, y, z)");
                Console.WriteLine("x= " + d1);
                Console.WriteLine("y= " + d2);
                Console.WriteLine("z= " + d3);
                Console.ReadLine();
            }
            else
            {
                Console.Write("wrong input");
                Console.ReadLine();
            }
        }
    }
}
