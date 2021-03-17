# Health-data

using System;

public class HealthProfile
{ 
    //declare all of the instance variables
    string _firstName;
    string _lastName;
    //string _dateOfBirthComplete;
    int _dayOfBirth;
    int _monthOfBirth;
    int _yearOfBirth;
    int _weightInPounds;
    int _heightInInches;
    string _gender;

    //constructor to initalize all the variables
    public HealthProfile(string FirstName, string LastName, int DayOfBirth, int MonthOfBirth, int YearOfBirth, int WeightInPounds, int HeightInInches, string Gender)
    {
        this._firstName = FirstName;
        this._lastName = LastName;
        this._dayOfBirth = DayOfBirth;
        this._monthOfBirth = MonthOfBirth;
        this._yearOfBirth = YearOfBirth;
        this._weightInPounds = WeightInPounds;
        this._heightInInches = HeightInInches;
        this._gender = Gender;
    }  // end constructor for HealthProfile

    //set and get _dayOfBirth
    public int DayOfBirth
    {
        get
        {
            return _dayOfBirth;
        }
        set
        {
            this._dayOfBirth = value;
        }
    }
    public void DisplayDayOfBirth()
    {
        Console.WriteLine("Day of Birth: {0}", DayOfBirth); 
    }

    //set and get _monthOfBirth
    public int MonthOfBirth
    {
        get
        {
            return _monthOfBirth;
        }
        set
        {
            this._monthOfBirth = value;
        }
    }
    public void DisplayMonthOfBirth()
    {
        Console.WriteLine("Month of Birth: {0}", MonthOfBirth);
    }

    //set and get _yearOfBirth
    public int YearOfBirth
    {
        get
        {
            return _yearOfBirth;
        }
        set
        {
            this._yearOfBirth = value;
        }
    }
    public void DisplayYearOfBirth()
    {
        Console.WriteLine("Year of Birth: {0}", YearOfBirth);
    }

    // set and get _firstName
    public string FirstName
    {
        get
        {
            return _firstName;
        }
        set
        {
            _firstName = value;
        }
    }
    //method to display the FirstName
    public void DisplayFirstName()
    {
        Console.WriteLine("First Name: {0}", FirstName);
    }

    //set and get last name
    public string LastName
    {
        get
        {
            return _lastName;
        }
        set
        {
            this._lastName = value;
        }
    }
    public void DisplayLastName()
    {
        Console.WriteLine("Last Name: {0}", LastName);
    }

    //set and get weight in pounds
    public int WeightInPounds
    {
        get
        {
            return _weightInPounds;
        }
        set
        {
            this._weightInPounds = value;
        }
    }
    public void DisplayWeightInPounds()
    {
        Console.WriteLine("Weight in pounds: {0}", WeightInPounds);
    }

    //set and get height in inches
    public int HeightInInches
    {
        get
        {
            return _heightInInches;
        }
        set
        {
            this._heightInInches = value;
        }
    }
    public void DisplayHeightInInches()
    {
        Console.WriteLine("Height in inches: {0}", HeightInInches);
    }

    //set and get gender
    public string Gender
    {
        get
        {
            return _gender;
        }
        set
        {
            this._gender = value;
        }
        
    }
    public void DisplayGender()
    {
        Console.WriteLine("Gender is: {0}", Gender);
    }


    //create a method that calculates the BMI
    public float BodyMassIndex()
    {
        float BMI = (WeightInPounds * 703) / (HeightInInches * HeightInInches);
        return BMI;
    }
    public void DisplayBodyMassIndex()
    {
        Console.WriteLine("Body Mass Index: {0}", BodyMassIndex());
    }
    public void DisplayBMIOutput()
    {
        //Perform IF, ELSE IF statements to provide the weight category
        if (BodyMassIndex() < 18.5)
        {
            Console.Write("\nYou are Underweight.\n");
        }//end if
        else if (BodyMassIndex() < 25)
        {
            Console.Write("\nYou weight is Normal.\n");
        }//end else if 
        else if (BodyMassIndex() < 30)
        {
            Console.Write("\nYou are Overweight\n");
        }//end else if
        else Console.Write("\nYou are Obese.\n");
    }
    public void DisplayBMIChart()
    {
        Console.Write("\n\n\nBMI Values\n\nUnderweight: less than 18.5\nNormal: between 18.5 and 24.9\nOverweight: between 25 and 29.9\nObese: 30 or greater\n");
    }

    //create method to calculate age
    public int YearsOfAgeSimple()
    {
        int YearsOfAgeSimple = (2014 - this._yearOfBirth);
        return YearsOfAgeSimple;
    }
    public void DisplayYearsOfAgeSimple()
    {
        Console.WriteLine("{0} years of age.", YearsOfAgeSimple());
    }


    //create method to calculate the Max heart rate
    public double MaxHeartRate()
    {
        int MaxHeartRate = (220 - YearsOfAgeSimple());
        return MaxHeartRate;
    }
    public void DisplayMaxHeartRate()
    {
        Console.WriteLine("Max heart rate: {0}", MaxHeartRate());
    }

    //create method to calculate the Target heart rate
    public double TargetHeartRate()
    {
        double TargetHeartRate = (.68 * MaxHeartRate()); // assume approx. average of 50 to 85% of max heart rate. 
        return TargetHeartRate;
    }
    public void DisplayTargetHeartRate()
    {
        Console.WriteLine("Target heart rate: {0}", TargetHeartRate());
    }
} // end class HealthProfile


//create the program to test out the class

class HealthProfileTest
{
    public static void Main(string[] args)
    {
        HealthProfile hp1 = new HealthProfile(null, null, 0, 0, 0, 0, 0, null);

        Console.Write("Enter First Name: ");
        hp1.FirstName = Convert.ToString(Console.ReadLine());
        Console.Write("Enter Last Name: ");
        hp1.LastName = Convert.ToString(Console.ReadLine());
        Console.Write("Enter Day of Birth: ");
        hp1.DayOfBirth = Convert.ToInt32(Console.ReadLine());
        Console.Write("Enter Month of Birth: ");
        hp1.MonthOfBirth = Convert.ToInt32(Console.ReadLine());
        Console.Write("Enter Year of Birth: ");
        hp1.YearOfBirth = Convert.ToInt32(Console.ReadLine());
        Console.Write("Enter Weight in pounds: ");
        hp1.WeightInPounds = Convert.ToInt32(Console.ReadLine());
        Console.Write("Enter Height in inches: ");
        hp1.HeightInInches = Convert.ToInt32(Console.ReadLine());
        Console.Write("Enter Gender: ");
        hp1.Gender = Convert.ToString(Console.ReadLine());

        
        
        hp1.DisplayFirstName();
        hp1.DisplayLastName();
        hp1.DisplayDayOfBirth();
        hp1.DisplayMonthOfBirth();
        hp1.DisplayYearOfBirth();
        hp1.DisplayWeightInPounds();
        hp1.DisplayHeightInInches();
        hp1.DisplayGender();
        hp1.DisplayYearsOfAgeSimple();
        hp1.DisplayMaxHeartRate();
        hp1.DisplayTargetHeartRate();
        hp1.DisplayBodyMassIndex();
        hp1.DisplayBMIOutput();
        hp1.DisplayBMIChart();        
    }
}
