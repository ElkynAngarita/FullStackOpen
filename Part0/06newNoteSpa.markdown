```mermaid

---
title: New note diagram on the page (SPA)
---

sequenceDiagram

user->>browser: Type a new note and clik on send
participant browser
participant server

Note right of browser:  JS instructs the code to get the form element from the page<br/>and register an event handler
Note right of browser: Event Handler  Avoids default handling of form submission
Note right of browser: Event Handler Creates a New Note<br/> Renders the list of notes on the page<br/> and sends the new note to the server
Note right of browser: POST /exampleapp/new_note_spa HTTP/1.1<br/>Content-type: application/json

browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
activate server
server-->>browser: HTTP/1.1 201 Created ... 
deactivate server

Note left of server: content-type: application/json ... charset=utf-8

```
