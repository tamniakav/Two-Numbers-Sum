using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Exam_6
{
    class Program
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());
            int m = int.Parse(Console.ReadLine());
            int magicNum = int.Parse(Console.ReadLine());

            int sum = 0;
            int numR = (n - m) + 1;
            int numRo = 0;
            int x = 0;
            int y = 0;

            for (int i = n; i >= m; i--)
            {
                for (int j = n; j >= m; j--)
                {
                    sum = i + j;

                    if (sum == magicNum)
                    {
                        x = i;
                        y = j;
                        numRo = (n - i) * (n - j);
                        if (n - i == 0)
                        {
                            numRo = (n - j) + 1;
                        }
                        else if (n - j == 0)
                        {
                            numRo = (n - j) * numR;
                        }
                        else
                        {
                            numRo = (n - i) * numR + ((n - j) + 1);
                        }
                        break;
                    } 
                }
                if (sum == magicNum)
                {
                    break;
                }
            }
            if (sum == magicNum)
            {
                Console.WriteLine("Combination N:{0} ({1} + {2} = {3})", numRo, x, y, magicNum);
            }
            else
            {
                Console.WriteLine("{0} combinations - neither equals {1}", numR * numR, magicNum);
            }
        }
    }
}
