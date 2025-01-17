using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace participation1INFO2200
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Welcome to Holly's State Capital Lookup App");
            Console.WriteLine();

            Console.Write("Please enter a state and I will return the capital (x to exit): ");
            string userinput = Console.ReadLine();

            Dictionary<string, string> stateCapDict = new Dictionary<string, string>();

            while (userinput != "x")
            {
                StreamReader reader = new StreamReader("statecaps.txt");
                while (!reader.EndOfStream)
                {
                    string line = reader.ReadLine();
                    string[] tempstatecaps = line.Split(',');
                    string state = tempstatecaps[0];
                    string capital = tempstatecaps[1];
                    stateCapDict.Add(state.ToUpper(), capital);
                }
                reader.Close();
            }

            if (stateCapDict.TryGetValue(userinput.ToUpper(), out string cap))
            {
                Console.WriteLine();
                Console.WriteLine($"State: {userinput}");
                Console.WriteLine($"Capital: {userinput}");
                Console.WriteLine();
            }
        }   else
    }       
                Console.WriteLine($"Could not fine {userinput} in the database");
            
}
 
