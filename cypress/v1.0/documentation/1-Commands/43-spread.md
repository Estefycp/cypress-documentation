slug: spread
excerpt: Spread an array as individual arguments to a callback function

# [cy.spead()](#section-usage)

The spread command allows an expression to be expanded in places where multiple arguments are expected. Similar to [`cy.then`](https://on.cypress.io/api/then)

***

# Usage

```javascript
cy
  .server()
  .route(/users/).as("getUsers")
  .route(/activities/).as("getActivities")
  .route(/comments/).as("getComments")
  .wait(["@getUsers", "@getActivities", "getComments"])
  .spread(function(getUsers, getActivities, getComments){
    // each XHR is now an individual argument
  })
```

***

# Related

- [then](https://on.cypress.io/api/then)
- [wait](https://on.cypress.io/api/wait)