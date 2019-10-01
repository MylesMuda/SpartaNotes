# Mon 30th Revision

## Sprint: Focused piece of work for 1-4 weeks
----------------------------------------------
Sprint Planning :   take project backlog - create Sprint backlog
                    work for the future
                    define tasks and what we mean by done
Daily Standup : YESTERDAY TODAY BLOCKERS
Sprint review : 1) Display result of sprint as a working version
                    a) MVP Minimum viable product
                    b) v1.0
                    c) v1.1 non breaking change
                    d) v2.0 breaking change
                2) Work done, work for the future (define done)
                3) Customer Facing process
Sprint retro :  Internal analysis of team strengths, weaknesses, future improvements
                What we thought of our own work

## Agile
--------
Working code over documentation
People over process
Collaboration over negotiation

Waterfall   : Linear lifecycle, good for smaller, repeatable, military or life-threatening projects
              Not good for consumer projects where business goals may shift from month to month
SDLC        : Software Development Lifecycle
                    1) Feasability Study (financial and technical)
                    2) Requirements gathering
                    3) Analysis
                    4) High Level design (architecture)
                    5) Low Level Design (specs)
                    6) Build/Implement
                    7) Test
                    8) Release
                    9) Maintain
                    10) Document
V-Model     : Testing at each stage
                    1) Code block = Unit > Unit testing
                    2) Units Join = Intergration testing
                    3) Working product = System testing
                    4) User Requirements = UAT - User acceptance testing

Kanban : reducing waste in warehouses also unused stock held
JIT : 24/7 processes e.g. manufacturing
Kanban board :  LIMITS number of active processes
                Backlog selected in development testing
                Approved, signed off
3 Pillars of Scrum : Transparency, Inspection, Adaptation
XP Extreme Programming : Pair programming (older version)

# OOP Pillars
Encapsulation - private fields in classes 
Abstraction - Accessing private fields in classes through public methods { get; set; }
Inheritance - Derived (child) classes iheriting properties from a Base (Parent) Class
Polymorphism - Optionally overriding the functionality from a Base class in a Derived class
Class - The blueprint for an object
Sealed - prevernts member from being inherited by derived classes
Abstract Class - A class that contains at least one abstract method
Abstract Method - A method with no implementation/code body
Concrete Class - A class with full implementation
Virtual - A function to override a member of a base class
Override - Altering the base functionality of the Base class 
Overload - Passing additional parameters to a method
Interface - Allows properties of a class to be implemented by other classes


User Story  : Scenario : As a... When I... Then
              As a user when I log in I see list of products
                Admin           List of users

# Testing
    Minimise defects
    Exhaustive  : Not possible to remove all defects

# Red Green Refactor
1) Red - Build tests, fail
2) Green - Write code to pass those tests
3) Refactor - Optimise code

White Box   : Inner working is visible - Input/output
Black Box   : Inner-working is hidden during testing

Alpha       : 1st Release - invitation to closed group e.g. stakeholders, press etc.
Beta        : pre-release - free for testing to the public
Regression  : Ensure latest code does not break older code

Error       : Logical error
Exception   1) Handled      : Try, Catch, Finally block
                try{ //dodgy code }
                catch(exeption e){ // exeption }
            1) Unhandled    : System visibly crashes
Failure     : Product does not meet the user requirements

Sprints:
BurnUp      : list of tasks DONE
BurnDown    : lists of tasks TO BE done