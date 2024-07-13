
## Part 0

The part number 0 of this challenge is make a new diagram that show the events on page
https://studies.cs.helsinki.fi/exampleapp/notes. In this case, a user need to write a
new info line and to click on submit button.

```mermaid
sequenceDiagram
    participant user
    participant browser
    participant server

    user->>browser: write Helsinki is lovely and click "submit"
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: confirmation of receipt of the new note
    deactivate server

    Note right of browser: the browser updates the list of notes without reloading the page

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Helsinki is lovely", "date": "2024-7-13" }, ... ]
    deactivate server

    Note right of browser: the browser renders the new note in the note list