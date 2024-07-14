
## Part 0 Third Diagram

SPA behavior after a user writes a new note

```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: Write note and click "submit"
    browser->>server: POST /new_note_spa with JSON payload
    activate server
    server-->>browser: 201 Created
    deactivate server

    Note right of browser: The browser updates the list of notes with the new note without reloading the page
