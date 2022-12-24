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

