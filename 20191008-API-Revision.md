# API's

## Goal today

    .NET Core
        Build API from scratch with SQLite

    Console app ==> read data as JSON

    Website ==> read data as JSON and display it on site

## What is an API?

Application Programming Interface

    A method of transferring web data across the internet

        PLAIN TEXT

        JSON {"FIELD": "VALUE"}

        XML <root><element field="value"></element></root>

    Yesterday we looked at serialising data to XML and back

    Today we are going to look at something similar but instead of just saving to a JSON file, we are going to EXPOSE ENDPOINTS in http where a client may obtain data.

    <form method="get/post"> //DEFINE IN HTML

    GET     /customers/     all
    GET     /customers/10   one with ID

    GET ==> data sent in URL visible to all

    POST    /customers/10   update
            /customers/10   delete

    DELETE
    PUT (Update)

    depends on the application : in basic html, they don't have delete/put

### Let's start with a simple model pulling in northwind and using scaffolding to build the API

Northwind Lab

    GET         /products/      YES
    GET         /products/78    YES
    POST        /products/      YES
    POST/PUT    /products/1     UPDATE??

## Consuming an API

    We're going to build a console app to 'consume' (use) our API

### Getting data from the internet

    The model in use is to get data ASCYNCHRONOUSLY (wait for it to come)

        Main thread ==> Async call generates a sub-thread (or TASK)

            Tasks have 2 types: 
                1) returns void
                2) returns Task<type>, to get the data we call myTask.result();

            Also, tasks returning a type must be declared in an async method where we await the web call. 

                async Task<myMethod()>{
                    await...
                    return...
                }
