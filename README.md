# SoftUni-Courses-BasicSintax...-Messages
using System;

namespace Messages
{
    class Program
    {
        static void Main(string[] args)
        {
            int tapper = 0;
            int nums = int.Parse(Console.ReadLine());
            string messages = string.Empty;
            for (int i = 0; i < nums; i++)
            {
                string tappers = Console.ReadLine();
                int tapperLength = tappers.Length;
                bool isPossible = Int32.TryParse(tappers, out tapper);
                if (isPossible)
                {
                    tapper = tappers[0] - '0' ;
                }
                else
                {
                    return;
                }
                int offset = (tapper - 2) * 3;
                if (tapper == 0)
                {
                    messages += (char)(tapper + 32);
                    continue;
                }
                if (tapper == 8 || tapper == 9)
                {
                    offset++;
                }
                int Index = offset + tapperLength - 1;
                messages += (char)(Index + 97);
            }

            Console.WriteLine(messages);
        }
    }
}
