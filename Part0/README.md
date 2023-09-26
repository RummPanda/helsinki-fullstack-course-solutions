# Part 0
> Helsinki University Fullstack Open Course [Part 0]([https://fullstackopen.com/](https://fullstackopen.com/en/part0/fundamentals_of_web_apps#exercises-0-1-0-6))

# 0.1: HTML
Review the basics of HTML by reading this tutorial from Mozilla: HTML tutorial.

This exercise is not submitted to GitHub, it's enough to just read the tutorial

# 0.2: CSS
Review the basics of CSS by reading this tutorial from Mozilla: CSS tutorial.

This exercise is not submitted to GitHub, it's enough to just read the tutorial

# 0.3: HTML forms
Learn about the basics of HTML forms by reading Mozilla's tutorial Your first form.

This exercise is not submitted to GitHub, it's enough to just read the tutorial

# 0.4: New note diagram
In the section Loading a page containing JavaScript - review, the chain of events caused by opening the page https://studies.cs.helsinki.fi/exampleapp/notes is depicted as a sequence diagram

The diagram was made as a GitHub Markdown-file using the Mermaid-syntax, as follows:

    sequenceDiagram
        participant browser
        participant server
    
        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
        activate server
        server-->>browser: HTML document
        deactivate server
    
        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server-->>browser: the css file
        deactivate server
    
        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
        activate server
        server-->>browser: the JavaScript file
        deactivate server
    
        Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server
    
        browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
        activate server
        server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
        deactivate server
    
        Note right of browser: The browser executes the callback function that renders the notescopy

# Solution
    sequenceDiagram
        participant browser
        participant server
    
        browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
        activate server

        Note left of server: The server reposnds with HTTP status code 302. <br> This is a URL redirect (the server creates HTTP GET request to the address defined in the header's location - the address "notes")
        
        server-->>browser: 302 Found
        deactivate server
    
        browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
        activate server
        server-->>browser: HTML code
        deactivate server
    
        browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
        activate server
        server-->>browser: main.css
        deactivate server

        browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
        activate server
        server-->>browser: main.js
        deactivate server

        Note right of browser: The browser starts executing the JavaScript code <br> that fetches the JSON from the server 
        
        browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
        activate server
        server-->>browser: [{ "content": "Hey there! I'm Panda, have a good day there :)", "date": "2023-09-26T09:30:22.9032"}, ... ]
        deactivate server
    
        Note right of browser: The browser executes the callback function that renders the note
![alt text](https://github.com/RummPanda/helsinki-fullstack-course-solutions/blob/main/Part0/0.4_NewNote_Diagram.png)

# 0.5: Single page app diagram
Create a diagram depicting the situation where the user goes to the single-page app version of the notes app at (https://studies.cs.helsinki.fi/exampleapp/spa).
![alt text](https://github.com/RummPanda/helsinki-fullstack-course-solutions/blob/main/Part0/0.5_Single_App_Page.png)

# 0.6: New note in Single page app diagram
Create a diagram depicting the situation where the user creates a new note using the single-page version of the app.
![alt text](https://github.com/RummPanda/helsinki-fullstack-course-solutions/blob/main/Part0/0.6_NewNote_SPA_Diagram.png)
