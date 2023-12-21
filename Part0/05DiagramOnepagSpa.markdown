```mermaid

---
title: Single-page application diagram  (SPA) https://studies.cs.helsinki.fi/exampleapp/spa
---

sequenceDiagram

participant browser
participant server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
activate server
server-->>browser:  HTML - Code 
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
activate server
server-->>browser: the main.css file
deactivate server

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
activate server
server-->>browser: the JavaScript file
deactivate server

Note right of browser: The browser starts executing the JavaScript<br/>code that fetches the JSON from the server<br/>xhttp.open("GET", "/exampleapp/data.json", true)<br/>xhttp.send()

browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
activate server
server-->>browser: [{ "content": "notes spa pag", "date": "2023-1-1" }, ... ]
deactivate server

Note right of browser: The browser executes the callback<br/>function that renders the notes



```
