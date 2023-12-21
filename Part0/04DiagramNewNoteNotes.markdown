```mermaid
sequenceDiagram

    user->>browser: Type a new note and clik on send
    participant browser
    participant server
 
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note left of server:  The server prompts the browser<br/>to make a new request
    server-->>browser: HTML document /exampleapp/notes - 302 Found
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser:  HTML - Code 
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the main.css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript<br/>code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "notes spa", "date": "2023-1-1" }, ... 100 notes]
    deactivate server

    Note right of browser: The browser executes the callback<br/>function that renders the notes
```
