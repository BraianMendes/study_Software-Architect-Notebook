# Folder Structures to Know

## All in One Place Folder Structure
To illustrate why folder structures are important, let's build a dummy example API. We'll have a mock database of rabbits 🐰🐰 and the API will perform CRUD actions on it. We'll build this with Node and Express.

Here's our first approach, with no folder structure at all. Our repo will be composed of the node modules folder, and the app.js, package-lock.json and package.json files.

Within our app.js file we'll have our tiny server, our mock DB, and two endpoints:

```
// App.js
const express = require('express');

const app = express()
const port = 7070

// Mock DB
const db = [
    { id: 1, name: 'John' },
    { id: 2, name: 'Jane' },
    { id: 3, name: 'Joe' },
    { id: 4, name: 'Jack' },
    { id: 5, name: 'Jill' },
    { id: 6, name: 'Jak' },
    { id: 7, name: 'Jana' },
    { id: 8, name: 'Jan' },
    { id: 9, name: 'Jas' },
    { id: 10, name: 'Jasmine' },
]

/* Routes */
app.get('/rabbits', (req, res) => {
    res.json(db)
})

app.get('/rabbits/:idx', (req, res) => {
    res.json(db[req.params.idx])
})

app.listen(port, () => console.log(`⚡️[server]: Server is running at http://localhost:${port}`))

```

If we test the endpoints we'll see they work perfectly fine:

```
http://localhost:7070/rabbits

# [
#   {
#     "id": 1,
#     "name": "John"
#   },
#   {
#     "id": 2,
#     "name": "Jane"
#   },
#   {
#     "id": 3,
#     "name": "Joe"
#   },
#   ....
# ]

###

http://localhost:7070/rabbits/1

# {
#   "id": 2,
#   "name": "Jane"
# }

```

So what's the problem with this? Nothing, actually, it works just fine. The problem will only arise when the codebase gets bigger and more complex, and we start adding new features to our API.

Similarly to what we talked about before when explaining monolithic architectures, having everything in a single place is nice and easy at first. But when things start getting bigger and more complex, this is a confusing and hard to follow approach.

Following the modularity principle, a better idea is to have different folders and files for the different responsibilities and actions we need to perform.



## Layers Folder Structure

Layers architecture is about dividing concerns and responsibilities into different folders and files, and allowing direct communication only between certain folders and files.

The matter of how many layers should your project have, what names should each layer have, and what actions should it handle is all a matter of discussion. So let's see what I think is a good approach for our example.

Our application will have five different layers, which will be ordered in this way:

* The application layer will have the basic setup of our server and the connection to our routes (the next layer).
* The routes layer will have the definition of all of our routes and the connection to the controllers (the next layer).
* The controllers layer will have the actual logic we want to perform in each of our endpoints and the connection to the model layer (the next layer, you get the idea...)
* The model layer will hold the logic for interacting with our mock database.
* Finally, the persistence layer is where our database will be.

You can see this approach is much more structured and has a clear division of concerns. This may sound like lots of boilerplate. But after setting it up, this architecture will allow us to clearly know where each thing is and which folders and files are responsible for each action our application executes.

An important thing to keep in mind is that in these kind of architectures there's a defined communication flow between the layers that has to be followed for it to make sense.

This means that a request first has to go through the first layer, then the second, then the third and so on. No request should skip layers because that would mess with the logic of the architecture and the benefits of organization and modularity it gives us.

## MVC Folder Structure

MVC is an architecture pattern that stands for Model View Controller. We could say the MVC architecture is like a simplification of the layers architecture, incorporating the front-end side (UI) of the application as well.

Under this architecture, we'll have only three main layers:

* The view layer will be responsible for rendering the UI.
* The controllers layer will be responsible for defining routes and the logic for each of them.
* The model layer will be responsible for interacting with our database.

## Sources

An Introduction to Software Architecture Patterns: https://www.freecodecamp.org/news/an-introduction-to-software-architecture-patterns/