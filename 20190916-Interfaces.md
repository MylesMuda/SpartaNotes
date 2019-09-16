20190916-Interfaces
	1)SQL 2 Tables, relational
	2) CRUD App, V1 Console, V2 WPF
	3) Create 1000 objects
		a) one using(var db) reads, time it with stopwatch
		b) 1000 using(var db) reads x 1000, time with stopwatch
	4) Canvas image becomes animated when complete
	5) BONUS: Report A) CSV B) Word report??

# Interfaces
Classes
	CONCRETE
		class{
		FIELDS
		PROPERTIES
		METHODS
	}
	ARE ALL COMPLETE - can instanciate the object with the new keyword which calls the constructor method.

	ABSTRACT CLASS
		class{
			Has at least one abstract method(a method with no body)
			must be instanciated with an override
		}
-
	INTERFACE
		A fully abstact class with ABSOLOUTELY no code body in methods
		interface InterfaceDoThis{
			(((abstract))) void DoThis();
		}
		(((abstract))) is implied, not stated
-
	Parent abstract class
	Okay to have a CHILD CONCRETE class : Can ONLY be a child of ONE PARENT
	Child : also can not just INHERIT from one parent, it can also implement (use) many interfaces.
-
	Parent Abstract Person{} 	//absract
	Child User : Person{}		//concrete
	Child User : Person, IUseThis, IUseThat {} //Implement 2 interfaces
-
	Interface IUseThis{void IDoThis();}
	Interface IUseThat{void IDoThat();}
-
	In the user class we have to IMPLEMENT (build) code for these interface methods IDoThis and IDoThat. Mind picture: each individual wukk use a tool in a slightly different way. 
-
	Interfaces are useful in large applications because they create standardisation of how classes will have expected behaviour.
		int.ToString();
		car.ToString();
-
		child.DoThis();
		child.DoThat();