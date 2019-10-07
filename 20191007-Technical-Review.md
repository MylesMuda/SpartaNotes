# Technical Review

Why are you at Sparta?

    1) Gain experience working as a software developer
    2) Upskill my coding and presentation skills

Strengths?

    Communication skills, presentation skills, strong coding background
    Acted as social chair, helped organise/co-ordinate event while training

Weaknesses?

    Lack of awareness of how to work as a professional software engineer on a real-world project, wish to gain more experience doing this in industry

Project Work of Note

    Games week project while at sparta global, game during university, digital clock while at university

Why do you like coding?

    Enjoy problem solving with purpose, make something that completes a useful task/creative outlet

Code out Fizzbuzz

```cs

Public class FizzBuzz{

    public string s;

    For(i = 0; i > 100; i++){
        if(i % 3 == 0){
            s += "Fizz";
        }
        if(i % 5 == 0){
            s += "Buzz"
        }
        if(i == ""){
            s = i.ToString();
        }
        Console.WriteLine(s);
    }

}
```

What is a:

    Class: Blueprint of an object
 
    Instance: An object created by the constructor of a class.

    Sealed Class: A class only accessible within a given DLL/Exe

    Abstract Class: A class with at least one abstract method that cannot be instanciated. 

    Virtual Keyword: used in a method which can be overwritten

    Override Keyword: derived method implements own functionality compared with parent base class method.

    Overloading: same method, different parameters

    OOP 4 Pillars
        Inheritance
        Polymorphism
        Encapsualation
        Abstraction

    Scrum 3 Pillars

        Adaptaption
        Inspection
        Transparency

    Agile - adaptable, flexible work in sprints
        Collaboration over Negotiation
        Working Code over Documentation
        People over Process
    
    Scrum 3 Roles
        Srcum Master - Ensure smooth workflow, remove blockers
        Product Owner - Owns product/project backlog (List of requirements) Also sprint backlog
            Definition of done by dev team - get approved here
        Devs (3-9) - Multi-skilled, Self organising, Jointly accountable

    Sprint - Focused period of work (1-4 weeks)
    Sprint 4 Meetings - Plan (plan the ), Daily (yesterday, today, blockers), Review (external - to clients/stakeholders), Retrospective (internal)
    SDLC : [Feasability]
        Requirements, Analysis, Planning, Design, Build, Test, Release, Maintain, Document

    Waterfall: linear
    Agile : adapt to change
    Kanban: 24/7 rolling with limit in Current Tasks
    JIT: Just in time, reduce warehouse waste

    Abstract Class
        Abstract Method
            OVERRIDE IS MANDATORY FOR DERIVED CLASSES

    ABSTRACT IS MANDATORY
    VIRTUAL IS OPTIONAL

    SOLID: best to have one method only (S = Single RESPONSIBILITY)
    
    S : one class is responsible for one thing
    O : Open for extension / closed modification
    L : Liskov
    I : Interfaces, one method only
    D : Dependancy Injection (Parent/Child interchange)

    API
        get     /customers/         SQL Select *
        get     /customers/10       SQL Select 1
        post    /customers/         SQL Insert
        post    /customers/10       SQL Update

        put     /customers/10       Update
        delete  /customers/10       Delete

    CRUD - create, read, update, delete
    SQL - INSERT, SELECT, UPDATE, DELETE
    SQL Database - Create, Drop IF EXISTS, Alter (table)



    ENUM

    STRUCT

Large Project Structure

    .sln                SOLUTION

    Main.exe            App that runs
        private classes
        public classes
        REFERENCE Library.dll and use its classes
    Library.dll
        public classes used in multiple projects

    DLL or EXE in called ASSEMBLY

        ASSEMBLY has a version and also is signed by a computer certificate

            Allows computer to differentiate versions of the same name but different versions

                MyApp       v1.0.1
                MyApp       v1.0.2  

```cs
using System;
using System.Reflection;

namespace lab_46_assemblies
{
    class Program
    {
        static void Main(string[] args)
        {
            //use integer type as an example
            var mytype = typeof(int);
            //lets find the DLL where INT lives in windows
            //IE Assembly
            var myAssembly = Assembly.GetAssembly(mytype);
            Console.WriteLine($"Assembly is called {myAssembly.GetName()}\n\n");
            // Check out all other types in the same assembly and print them out
            foreach(var type in myAssembly.GetTypes())
            {
                Console.WriteLine(type);
            }
        }
    }
}
```

## Encoding

File Extensions

    .txt
    .jpg

    Rename myFile.txt to myFile.jpg what is it? It's still a TEXT FILE.

File Signatures

    Pattern of 1's and 0's at the start of a file when it's laid down on disk that indicates the file type

    File signatures are publicly known

        Drive recovery programs can scan the disk for known signatures in order to recreate deleted files

    ASCII

        USA built the first computers ==> US English is the default character set on the web

        7 Bits ie numbers from 0 - 127

            (int)char will yeild this number

    UTF8

        Add a 0 at the end of the ASCII, 0 then 7 bits

        The web is built exclusively from UTF8 character set

            Getbootstrap.com ==> <meta charset ="utf-8">

        BASE64 is used to transport all data that is not in this simple character set

        <<Complex data>> ==> chop it into blocks of 6 bits wide

                         ==> each 6 bit block is allocated an ascii letter

                         ==> Send data as ascii

                         ==> Process is reversed at the recieving end

    UTF16

        Russian, chinese languages etc have many characters

        Using 16 bits we can now describe most characters in the world

        ASCII 2^7 = 128

        UTF16 = 2^16 = 65536

    UNICODE = UTF16
    
    C# .NET Coding default encoding is 16 bit

    SecureString cna be used as an input type which is slightly more secure than standard. 
    No strings are completely secure however.

## Streaming and serialisation

Getting data across the internet

We can stream to local file system

    .net runtime will think of the harddrive as a remote system

    Therefore you can implement streaming to and from the harddrive.

        When encrypting data, stake raw data, scramble it and put it somewhere

        Quite often data is not stored on the harddrive, but in memory of the local computer ie RAM

Memory is different because we can allocate a fixed number of bytes for the data

    We can also allocate the START byte and the FINISH byte exactly, therefore we can have a pointer at a set position for that data.

Network

  - http://           web
  - https://          secure web
  - ftp://            files
  - smb://            shares
  - //server/share    shares

ASYNC

    More common today, will not wait, will continue so the user feels as though the app is still responsive
    Data will return and another method, called the callback method, will run.
    EACH ASYNC CALL HAS A CALLBACK METHOD ATTACHED TO IT

SYNC

        Will wait for the operation, will pause/hang the whole program

How much does the programmer get involved?

    Almost none.

    Make call and let OS handle it: Programmer handles the incoming data.

## Serialisation

Converting data into a form for streaming, a linear sequence of 1's and 0's to be sent across the internet.

Customer Object

    ==> Serialise part of it 101010100101010

    ==> SEND

    ==> Unpack ==> Recreate customer at the other end (Deserialisation)

    CUSTOMER => SERIALISE => STREAM => DESERIALISE

Can serialise to 3 types of data for sending

    1) XML        UTF-8 - primarily for the web 
    2) JSON       UTF-8 - ^^^, Can use NEWTONSOFT.JSON (3rd party library)
    3) BINARY     10101010101010 - fastest type as there is no data conversion, RAW DATA,                                      primarily for ram/memory

    Files can be any of these three or other filetypes.

## LOOK AT JAVASCRIPT FETCH
