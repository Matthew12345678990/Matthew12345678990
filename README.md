using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> generatedPins = new List<string>();

        // Wygeneruj 10 unikalnych PIN-ów
        for (int i = 0; i < 10; i++)
        {
            string pin = GeneratePin(generatedPins);
            generatedPins.Add(pin);
            Console.WriteLine($"Generated PIN: {pin}");
        }

        Console.ReadLine();
    }

    static string GeneratePin(List<string> existingPins)
    {
        Random random = new Random();
        string pin;

        do
        {
            // Generuj losowy czterocyfrowy PIN
            int randomPin = random.Next(1000, 10000);
            pin = randomPin.ToString("D4");

        } while (existingPins.Contains(pin)); // Sprawdź, czy PIN już istnieje

        return pin;
    }
}
