sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Note right of browser: Post request contains content and date (not through default form behaviour)
    activate server
    server-->>browser: JSON Data, indicated by application/json in Content-Type
    deactivate server

    Note right of browser: The browser handles the data by adding a new note through notes.push(note)