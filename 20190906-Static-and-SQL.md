20190906 - Static and SQL

# OOP Revision
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

library MYLIBRARY.DLL
		internal : use within this DLL but not outside of it

# Static

	class MyClass{
		private int _hiddenField;
		public string property{get;set;}
		public void Method(){}

		public MyClass(){}
	}

	var m = new MyClass(){} //constructor
	m is an instance of MyClass
	m.Property;	
	m.Method;

	Math.PI();
	Math.Random();
	Math.Round();

	STATIC MEMBERS ATTATCHED TO THE MATH CLASS

	class MyClass{
		static public int Property{get;set;}	CLASS/STATIC
		static public void DoThis();			CLASS/STATIC
	}

	MyClass.Poperty();	These DON'T change in relation to instances of the class
	MyClass.DoThis();

Mind Picture
	user(instance) personal shopping basket
	static count of the total items in stock
	Not related to users but global to the store


# SQL - Structured Query Language

Microsoft	:	MS-SQL
Free 		:	MySQL			

Relational Databases
	
	Tables
		ID;
		Fields;

	User
		UserID;
		Username;

	Category
		CategoryID;
		CategoryName;

	We can create relationships between two tables

		User
		UserID;
		Username;
		CategoryID; 	Foreign Key, ID from another table

	ID = Identity : Unique, Auto-increment to highest value

Today's proposal
	SQL : Create database with some rabbit tables
	Entity : C# can be hooked into this database
				able to view, update Rabbits

SQL Commands:

	View > Server Explorer > Data Connection, Add
		(localdb)\mssqllocaldb

	View > SQL Object Explorer
		Gives access to the local computer using SQL server
		Files are called .mdf microsoft data file
		Stored in the C:\Users\%username% folder

```SQL
use RabbitDb
go

CREATE TABLE Rabbits(
	RabbitId INT NOT Null IDENTITY PRIMARY KEY,
	Age INT,
	Name VARCHAR(50) NULL 
);

select 'here is comment'

Update Rabbits Set Name = 'Greg' Where RabbitId = 1

Insert into Rabbits values (2, 'Thomas')

SET IDENTITY_INSERT Rabbits ON

delete from Rabbits where RabbitId=2

select * from Rabbits

```

# Connecting to a Database

Microsoft can connect directly to a database using Entity Framework

EF6 : Framework
EFCore : Lighter version, more open source

If we begin using EF6, there is more support so it's easier to get going

1) New Console App (Framework)

2) Create entity

3) Connect to database

4) View rabbits

```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace lab_19_rabbit_database_explosion
{
    class Program
    {
        static List<Rabbit> rabbits;
        static void Main(string[] args)
        {

            using (var db = new RabbitDbEntities())
            {
                rabbits = db.Rabbits.ToList();
            }

            PrintRabbits();

            var newRabbit = new Rabbit()
            {
                Age = 0,
                Name = $"Jeff{rabbits.Count+2}"
            };

            using (var db = new RabbitDbEntities())
            {
                db.Rabbits.Add(newRabbit);
                db.SaveChanges();
            }

            System.Threading.Thread.Sleep(200);
            using ( var db = new RabbitDbEntities())
            {
                rabbits = db.Rabbits.ToList();
                
                PrintRabbits();
            }
            Console.ReadLine();   
        }
        static void PrintRabbits()
        {
            rabbits.ForEach(rabbit => Console.WriteLine($"{rabbit.RabbitId,-5}" + $"{rabbit.Name,-12}{rabbit.Age}"));
        }
    }
}
```

# Homework
New WPF Just_Do_It_Rabbit_12_Explosion using the .net framework
Add 2 text boxes (age and name) and an add button
Add Entity 
When you click the add button 
	ADD a new rabbit
	Display a rabbit picture for ONE SECOND

Create a textblock and do a foreach loop to output the rabbit data into this text block

Needs to be linked with the database

Ideas
-----
Add a timer?
start adding our own rabdom rabbits
do it using CANVAS, not GRID

https://www.wpf-tutorial.com/panels/canvas/ //check this link

Due Monday??