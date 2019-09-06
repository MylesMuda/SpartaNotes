20190906 - Static and SQL

# Static
Class myClass{
	private int `_hideMe`;	//private field (OOP Encapsulation)

	public string Name {get;set;} public property (OOP abstraction. Abstract layer to give get and set access to a private field)

	public void DoThis();

}

abstract class Idea{
	abstract void DoThis(); //no code body or implementation
}

class solidThoughts : Idea{
	override void DoThis(){} //with code body
}

ABSTRACT CLASSES cannot be instanciated
CONCRETE (Regular) CLASS can be

	var m = new MyClass();

OOP Polymorphism
	Parent 	:	virtual (has a body)
	Child 	:	override (optional)

OOP Abstract
	Parent	:	abstract (empty)
	Child	:	override (mandatory)

OOP Inheritance

Access modifiers: 	public 		: See from anywhere
					private 	: hidden inside class
					protected 	: hidden inside class and derived in child classes
					internal	: within compiled EXE/DLL - visible in this scope

