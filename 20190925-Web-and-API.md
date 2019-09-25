# Web

The web realm is extremely exciting
    Check out BLAZOR which is C# running natively in the browser

    Today we're checking out API's which power much of the web

    Website
        For human consumption
        HTML structure
        CSS colour, animations
        JavaScript code

    API (Application Programming Interface)
        For machine consumption
        Data in the form of
        1) JSON
        2) XML

```JSON
    {
        "field":value,
        "field":value
    }
    [   //an array
        {
        "field":value,
        "field":value
        },
        {
        "field":value,
        "field":value
        }   
    ]
```
```XML
    <rootElement>
        <item length="1">
            <field otherValue="admin">Value</field>
        </item>
    </rootElement>
```
<> tag, Element ((ONE ROOT ONLY))

Element with attribute (length) and value 1

Goal for today:
    1) Northwind
    2) Entity Framework
    3) Scaffold API from scratch with minimal work

# MVC Methodology
    Model
        Database Item ==> C# manifests as Class which matches the database table
        NorthWind Customers ==> Class Customer (The entity scaffolds for us)

    View
        Display of data to the end user : HTML/CSS/JavaScript + server side data fed into the page
        (translated into HTML/CSS/JS as well)
        
        Server                                    Client
        C#/Node/PHP/Java/Python
            Render
                Translates raw data into 
                form suitable for viewing
                ie HTML etc --------------------> sent to client for display
    
    Controller
        Looks at the URL to make sense of it
            https://www.mydomain.com/controller/action/id
                                    /customers/Get/         SELECT *
                                    /customers/Get/ALFKI    SELECT .. where id =ALFKI
                                    /customers/Post/        NEW customer
                                    /customers/Post/id      UPDATES customer
                                    Could be /Put/id
            GET: request VISIBLE in URL
            POST: request is already inside web data
        Controller
        a) Analyses URL
        b) According to the instructions in URL, fo and get relevant data from model
        c) Send that data to a view page which displays the data

# MVC Summary

MODEL:      Data
CONTROLLER: Takes request, returns the data to the VIEW
VIEW:       Display

# API using .NET Core

Microsoft is strongly pushing .NET Core
Let's use this opportunity to explore what it means to use .NET Core to read a database

Goals:
1) Use code first approach to build our code and, from this, create a database.
        a) SQLServer
        b) SQLite ==> Try this way this time.
2) Seed data from C# ie create a new database with new data
3) Create our API

# Setup
.NET Core 2.1 Web App with API
    Install libraries EntityFrameworkCore/SQLite/Design v 2.1.1
