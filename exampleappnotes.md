```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: 302 Redirect to /notes
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: main JavaScript file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/isolated-first.js
    activate server
    server-->>browser: JavaScript file (isolated-first.js)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/content.js
    activate server
    server-->>browser: JavaScript file (content.js)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/executor.js
    activate server
    server-->>browser: JavaScript file (executor.js)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/AtlassiansSans-latin.woff2
    activate server
    server-->>browser: Font file (woff2)
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON data

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: JSON file with notes data
    deactivate server

    Note right of browser: The browser executes the callback function to render the notes

```

    Note right of browser: The browser executes the callback function that renders the notes
