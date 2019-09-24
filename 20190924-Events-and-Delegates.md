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

