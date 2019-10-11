# Task 4: branching

Our first question asks the user how many balls they can juggle. We’re going to send them to an ‘ineligible’ page if they can only juggle 2 or less.

To do this, we’re going to need an `ineligible.html` page to send them to, and some logic to decide when to send them there.

The logic takes the answer the user has given to the first question, and depending on what the answer was, either show them the next question or send them to the ineligible page.

## Create the ineligible page

1. Make an `ineligible.html` page by copying `template-content-page.html`
2. Update the content to tell the user why they’re ineligible.
3. Update the back link to point at question 1
4. Check it works by visiting `https://localhost:3000/ineligible`

## Route users to the ineligible page

We’re going to write some logic to look at the user’s answer to question 1. If the user can juggle 3 balls or more (the first answer), we’ll show them question 2. If they answer with anything else, we’ll send them to the ineligible page.

Currently, the juggling-balls page sends the user directly to question 2. We’re going to instead send them to a new special url where we can run some code to check their answer.

1. In `juggling-balls.html` change the form action (line 16) to `/juggling-balls-answer`
2. Open /app/routes.js
3. Insert new javascript into line 5, before `module.exports = router`

```
router.post('/juggling-balls-answer', function (req, res) {

  // Make a variable and give it the value from 'juggling-balls'
  var jugglingBalls = req.session.data['juggling-balls']

  // Check whether the variable matches a condition
  if (jugglingBalls == "5 or more"){
    // Send user to next page
    res.redirect('/juggling-trick')
  }
  else {
    // Send user to ineligible page
    res.redirect('/ineligible')
  }

})
```

Check it works by testing each of the answers.

### If the kit crashes 

If you don’t get a page, check in the terminal to see if the kit has crashed. This is a common problem if there’s a typo in the javascript. Helpfully the kit will try to tell you the line number with the issue.

Sample terminal output:

```
/Users/yourname/projects/juggling-licence-prototype/app/routes.js:12
});
^
SyntaxError: Unexpected token }
    at Object.exports.runInThisContext (vm.js:76:16)
    at Module._compile (module.js:542:28)
    at Object.Module._extensions..js (module.js:579:10)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)
    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/Users/yourname/projects/juggling-licence-prototype/server.js:7:14)
    at Module._compile (module.js:570:32)
[14:11:50] [nodemon] app crashed - waiting for file changes before starting…
```
For example, the first line of this ends with `...juggling-licence-prototype/app/routes.js:12`

The 12 indicates there’s probably a mistake on line 12 or the line before it. In this case, it’s a missing bracket.
