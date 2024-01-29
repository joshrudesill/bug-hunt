# Node & Express Bug Hunt!

**READ ALL INSTRUCTIONS BEFORE STARTING**

There are 10 bugs in total, can you find them all? There are hints throughout (???), you should only need to make minor modifcations to 10 lines of code.

**Don't race through the files looking for the issues!** They should all have a console log or error that help you identify them. Read the console so that you know what error will cause each bug. The last one is tricky since it doesn't throw any errors. Document the error, line number and your fix in this README for each of the bugs.

## Setup

```
npm install
npm start
```

> NOTE: A couple of bugs prevent the server from starting.

## Error List

TODO: Add the error here followed by the line of code you fixed.

### Bug 0

`ReferenceError: app is not defined`

Fixed `quote.router.js` line 28: switch `app` to `router`. _This is the solution to the first bug._

### Bug 1

`TypeError: Router.use() requires a middleware function but got a Object`

Added `module.exports = router;` to quote router file

### Bug 2

`Failed to load resource: the server responded with a status of 404 (Not Found)`

Added `app.use(express.static("server/public"));` to server.js

### Bug 3

`GET http://localhost:5007/quotes%7D 404 (Not Found)`

updated ` axios({
    method: "GET",
    url: "/quotes", < there was a extra bracket here
  })`

### Bug 4

`GET http://localhost:5007/quotes%7D 404 (Not Found)`

removed `router.get("/", (req, res) => {` quotes from the route here

### Bug 5

`TypeError: quotesFromServer is not iterable`

`let quoteList = {};` to `let quoteList = [];`

### Bug 6

`POST http://localhost:5007/quotes 500 (Internal Server Error)`
`quotesList.push(quoteToAdd);` to `quoteList.push(quoteToAdd);`

### Bug 7

`.then((response) => {
      console.log(response);
      getQuote();
    })` to
`.then((response) => {
      console.log(response);
      getQuotes();
    })`

### Bug 8

Inputs dont clear after submit
add `document.querySelector("#authorInput").value = "";
      document.querySelector("#quoteInput").value = "";` in .then() of submitForm()

## Extra Practice (Optional)

Complete the JS debugging exercises at:

- https://education.launchcode.org/intro-to-professional-web-dev/chapters/errors-and-debugging/exercises.html
