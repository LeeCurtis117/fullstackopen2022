# part0
ExercisesPart0FullStackOpen2020

# 0.4: new note
Create a similar diagram depicting the situation where the user creates a new note on page https://fullstack-exampleapp.herokuapp.com/notes by writing something into the text field and clicking the submit button.

![0 4_ New note diagram](https://user-images.githubusercontent.com/18190404/209438303-fbbc8b26-75e9-4613-8687-5cb8ea77ecef.png)

title 0.4: New note diagram


browser->server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/notes
browser->server: [{ content: "I like learning", date: "2019-05-23" }, ...]
server-->browser: HTTP status code 302


note over browser:
When the button on the form is clicked, 
the browser will send the user input to the server
app.post('/new_note', (req, res) => {
  notes.push({
    content: req.body.note,
    date: new Date(),
  })

  return res.redirect('/notes')
}
end note

0.5: Single page app diagram
Create a diagram depicting the situation where the user goes to the single page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.

![0 5_ Single page app diagram](https://user-images.githubusercontent.com/18190404/209438497-27931926-0da0-4aa8-a6b7-8fb891870d9a.png)

title 0.5: Single page app diagram

browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
server-->browser: HTTP status 200 HTML-code
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa/main.css
server-->browser:   HTTP status 200 main.css
browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa/main.js
server-->browser:   HTTP status 200 main.js

note over browser:
browser starts executing js-code
that requests JSON data from server 
end note

browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa/data.json
server-->browser: [{ content: "HTML is easy", date: "2019-05-23" }, ...]

note over browser:
browser executes the event handler
that renders notes to display
end note


0.6: New note in Single page app diagram
Create a diagram depicting the situation where the user creates a new note using the single page version of the app.

![0 6_ New note in Single page app diagram](https://user-images.githubusercontent.com/18190404/209438696-68107377-9050-4b96-a136-2d2c4fd685d5.png)

title 0.6: New note in Single page app diagram

browser->server: HTTP get https://studies.cs.helsinki.fi/exampleapp/spa
server-->browser: HTTP status 200 HTML-code

note over browser:
In single page app,
browser stays on page 
no new HTTP request
end note

