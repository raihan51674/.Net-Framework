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
## question 
### সমস্যা (Problem) সংক্ষিপ্ত বিবরণ (Bangla):
- তিন প্রকার খেলোয়াড় থাকবে: Batsman, Bowler, এবং All-Rounder।

- বেস ক্লাস Player থাকবে যেটার ফিল্ডস: playerId, playerName, teamName এবং একটি ভার্চুয়াল মেথড ShowInfo().

- Batsman ক্লাসে অতিরিক্ত থাকবে: totalRuns, battingAverage, highestScore.

- Bowler ক্লাসে অতিরিক্ত থাকবে: totalWickets, bowlingAverage.

- All-Rounder ক্লাসে থাকবে: totalRuns এবং totalWickets.

- PlayerPerformance() মেথডের মাধ্যমে প্লেয়ারের পুরস্কারের যোগ্যতা নির্ণয় হবে:

- Batsman: battingAverage > 50 হলে যোগ্য।

- Bowler: totalWickets > 100 হলে যোগ্য।

- All-Rounder: totalRuns > 1000 এবং totalWickets > 50 হলে যোগ্য।

 -ShowInfo() মেথডে খেলোয়াড়ের তথ্য ও পুরস্কারের যোগ্যতা দেখাবে।
```cs
using System;

namespace ConsoleAppCricketWorldCup
{
    // Base Player class
    class Player
    {
        public string PlayerId { get; set; }
        public string PlayerName { get; set; }
        public string TeamName { get; set; }

        public Player(string playerId, string playerName, string teamName)
        {
            PlayerId = playerId;
            PlayerName = playerName;
            TeamName = teamName;
        }

        // Virtual method to show player info
        public virtual void ShowInfo()
        {
            Console.WriteLine($"Player ID: {PlayerId}");
            Console.WriteLine($"Player Name: {PlayerName}");
            Console.WriteLine($"Team Name: {TeamName}");
        }

        // Virtual method to check eligibility
        public virtual bool PlayerPerformance()
        {
            return false; // By default, not eligible
        }
    }

    // Batsman class inherits Player
    class Batsman : Player
    {
        public int TotalRuns { get; set; }
        public double BattingAverage { get; set; }
        public int HighestScore { get; set; }

        public Batsman(string playerId, string playerName, string teamName,
            int totalRuns, double battingAverage, int highestScore)
            : base(playerId, playerName, teamName)
        {
            TotalRuns = totalRuns;
            BattingAverage = battingAverage;
            HighestScore = highestScore;
        }

        public override void ShowInfo()
        {
            Console.WriteLine("🏏 Batsman Details:");
            base.ShowInfo();
            Console.WriteLine($"Total Runs: {TotalRuns}");
            Console.WriteLine($"Batting Average: {BattingAverage}");
            Console.WriteLine($"Highest Score: {HighestScore}");
            Console.WriteLine($"Eligible for Award: {(PlayerPerformance() ? "Yes" : "No")}");
        }

        public override bool PlayerPerformance()
        {
            return BattingAverage > 50;
        }
    }

    // Bowler class inherits Player
    class Bowler : Player
    {
        public int TotalWickets { get; set; }
        public double BowlingAverage { get; set; }

        public Bowler(string playerId, string playerName, string teamName,
            int totalWickets, double bowlingAverage)
            : base(playerId, playerName, teamName)
        {
            TotalWickets = totalWickets;
            BowlingAverage = bowlingAverage;
        }

        public override void ShowInfo()
        {
            Console.WriteLine("🎯 Bowler Details:");
            base.ShowInfo();
            Console.WriteLine($"Total Wickets: {TotalWickets}");
            Console.WriteLine($"Bowling Average: {BowlingAverage}");
            Console.WriteLine($"Eligible for Award: {(PlayerPerformance() ? "Yes" : "No")}");
        }

        public override bool PlayerPerformance()
        {
            return TotalWickets > 100;
        }
    }

    // All-Rounder class inherits Player
    class AllRounder : Player
    {
        public int TotalRuns { get; set; }
        public int TotalWickets { get; set; }

        public AllRounder(string playerId, string playerName, string teamName,
            int totalRuns, int totalWickets)
            : base(playerId, playerName, teamName)
        {
            TotalRuns = totalRuns;
            TotalWickets = totalWickets;
        }

        public override void ShowInfo()
        {
            Console.WriteLine("🔄 All-Rounder Details:");
            base.ShowInfo();
            Console.WriteLine($"Total Runs: {TotalRuns}");
            Console.WriteLine($"Total Wickets: {TotalWickets}");
            Console.WriteLine($"Eligible for Award: {(PlayerPerformance() ? "Yes" : "No")}");
        }

        public override bool PlayerPerformance()
        {
            return TotalRuns > 1000 && TotalWickets > 50;
        }
    }
}

Player[] players = new Player[4];
players[0] = new Batsman("P-1", "Tom Latham", "NZ", 6789, 57.3, 183);
players[1] = new Bowler("P-2", "Taskin Ahmed", "BD", 104, 23.2);
players[2] = new AllRounder("P-3", "Glenn Maxwell", "AUS", 7598, 98);
players[3] = new AllRounder("P-4", "Sam Curran", "ENG", 781, 60);

foreach (Player player in players)
{
    player.ShowInfo();
    Console.WriteLine();
}

```



