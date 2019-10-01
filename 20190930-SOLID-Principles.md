# Solid Programming Principles

Theoretical overview of good programming principles.
Becomes impotant on larger projects where up-front theoretical thinking and good practice can save a lot of refactoring work later.

S = Single Responsibility (a class chould be related to ONE class ONLY)

    class Rabbit    GOOD 
    class Kitchen   TOO VAUGE AS DIFFERENT, MUTUALLY EXCLUSIVE SUBTYPES
        KitchenOpenPlan     Mutually exclusive
        KitchenClosed

O = Open / CLosed 
    Open for EXTENSION (not sealed)
    CLosed for MODIFICATION (don't mess with your original work if possible)

    Class A_Class   parent : don't modify if possible
    Class ModelA13
    Class ModelA14  both modify original parent

L  = LISKOV : OK to replace child with parent instances

I = Interfaces : Small ie use one method per interface
    IENumerable : GetEnumerator (countable list with numeric index) : ONE METHOD ONLY 

D = Depend on Abstract Classes at the top of your structure rather than real classes

Overflow Exception

Summary : Reference, value types
    Stack   : primitives / value types / pointers (to heap)     FASTER  : Instant Data Disposal

    Heap    : Reference types                                   SLOWER  : Garbage collection at intervals