```cs
using System;
using System.Collections.Generic;

namespace VehicleApp
{
    class Vehicle
    {
        public string ModelNo { get; set; }
        public double Mileage { get; set; }
        public double CC { get; set; }

        public Vehicle(string modelNo, double mileage, double cc)
        {
            ModelNo = modelNo;
            Mileage = mileage;
            CC = cc;
        }

        public virtual void ShowDetails()
        {
            double dualConsumption = CC * Mileage;
            Console.WriteLine($"Model No: {ModelNo}");
            Console.WriteLine($"Mileage: {Mileage} km/l");
            Console.WriteLine($"CC: {CC}");
            Console.WriteLine($"Dual Consumption: {dualConsumption}");
        }
    }

    class Car : Vehicle
    {
        public Car(string modelNo, double mileage, double cc)
            : base(modelNo, mileage, cc) { }

        public override void ShowDetails()
        {
            Console.WriteLine("🚗 Car Details:");
            base.ShowDetails();
        }
    }

    class Truck : Vehicle
    {
        public Truck(string modelNo, double mileage, double cc)
            : base(modelNo, mileage, cc) { }

        public override void ShowDetails()
        {
            Console.WriteLine("🚚 Truck Details:");
            base.ShowDetails();
        }
    }

    class Bus : Vehicle
    {
        public Bus(string modelNo, double mileage, double cc)
            : base(modelNo, mileage, cc) { }

        public override void ShowDetails()
        {
            Console.WriteLine("🚌 Bus Details:");
            base.ShowDetails();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            List<Vehicle> vehicles = new List<Vehicle>();

            Console.WriteLine("আপনি কতটি গাড়ির তথ্য দিতে চান?");
            int n = int.Parse(Console.ReadLine());

            for (int i = 0; i < n; i++)
            {
                Console.WriteLine($"গাড়ি #{i + 1} এর ধরণ লিখুন (car/truck/bus):");
                string type = Console.ReadLine().Trim().ToLower();

                Console.WriteLine("Model No লিখুন:");
                string modelNo = Console.ReadLine();

                Console.WriteLine("Mileage (km/l) লিখুন:");
                double mileage = double.Parse(Console.ReadLine());

                Console.WriteLine("CC লিখুন:");
                double cc = double.Parse(Console.ReadLine());

                Vehicle vehicle = null;

                switch (type)
                {
                    case "car":
                        vehicle = new Car(modelNo, mileage, cc);
                        break;
                    case "truck":
                        vehicle = new Truck(modelNo, mileage, cc);
                        break;
                    case "bus":
                        vehicle = new Bus(modelNo, mileage, cc);
                        break;
                    default:
                        Console.WriteLine("ভুল গাড়ির ধরন দিয়েছেন। পুনরায় চেষ্টা করুন।");
                        i--; // loop index কমিয়ে আবার ইনপুট নিতে বলছে
                        continue;
                }

                vehicles.Add(vehicle);
                Console.WriteLine();
            }

            Console.WriteLine("আপনার দেওয়া গাড়ির তথ্যসমূহ:");

            foreach (Vehicle v in vehicles)
            {
                v.ShowDetails();
                Console.WriteLine("----------------------------");
            }

            Console.ReadLine();
        }
    }
}
```

