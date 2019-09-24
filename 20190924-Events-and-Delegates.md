# Events and Delegates

Scripting ==> Linear programming ==> line 1 to end

Graphics ==> screen objects eg button

	Event driven programming 

	<Button x:Name="Button01" Click="DoThis">

	static void Main(string[] args){
		private void Button01_Click(object sender, EventArgs e){
			//sender: Object INSTANCIATING the event
			//EventArgs: 
		}
	}

a) Trivial example
b) OOP example

# Trivial Event
1. Event can trigger one or more method(s). Don't declare a method DIRECTLY but via an "agent" type which will call named methods.

	A Delegate is a POINTER object which points to one or more methods.

	Declare delegate ==> creates a fixed structure for permitted in/out parameters. 
```cs
		delegate void MyDelegate(); //pointer to methods but ONLY methods matching this form can be part of a delegate object.

		// YES void DoThis();
		// YES void DoThat();
		// NO int AlsoDoThis(){return 1;}
```
Specification / signature of method is in/out parameter mix

2. Declare an event but also specify the input and output parameters for ANY method which will be called.

```cs
	Public event MyDelegate MyEvent;
```

3. Attach methods to our event (must match given in/out structure)
```cs
	MyEvent += Method01; //Add methods to delegate
	MyEvent += Method02;
	...
	MyEvent -= Method01; //Remove methods from delegate
```

# Trivial Example

```cs
using System;

namespace lab_34_events
{
    class Program
    {

        public delegate void MyDelegate();

        public static event MyDelegate MyEvent;

        static void Main(string[] args)
        {
            MyEvent += MethodA; //Callback: A pointer to a method but don't call the method right away.            
            MyEvent += MethodB;            
            MyEvent += MethodC;
            MyEvent();
            MyEvent -= MethodA;
            MyEvent();
        }

        static void MethodA() { Console.WriteLine("Method A"); }
        static void MethodB() { Console.WriteLine("Method B"); }
        static void MethodC() { Console.WriteLine("Method C"); }
    }
}
```
# OOP Example with instances

```cs
using System;

namespace lab_35_oop_events
{
    class Program
    {
        static void Main(string[] args)
        {
            var Jame = new Child();
            Jame.Name = "Jame";
            Jame.Grow("NO");

            for(int i = 0; i < 10; i++)
            {
                Jame.Grow($"SPACE {i}");
            }
        }

        class Child
        {
            public delegate int BirthdayDelegate(string TypeOfParty);
            public event BirthdayDelegate HaveBirthday;

            public string Name { get; set; }
            public int Age { get; set; }

            public Child()
            {
                this.Age = 0;
                Console.WriteLine("Congratulations, BEAUTIFUL baby :)");
                HaveBirthday += Celebrate;
            }

            int Celebrate(string TypeOfParty)
            {
                Age++; //one year older
                Console.WriteLine($"Celebrating yet another birthday! Age: {Age} Type of Party: {TypeOfParty}");
                return Age;
            }

            public void Grow(string TypeOfParty)
            {
                int ageNow = HaveBirthday(TypeOfParty);
            }
        }
    }
}
```
