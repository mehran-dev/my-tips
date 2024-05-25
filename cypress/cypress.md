### Now or Never

node_modules/.bin/cypress open

or cypress open

```javascript
describe("",()=>{

    beforeEach(()=>{
        cy.visit(/)
    })


    it("",()=>{
        cy.visit("/")
        cy.focused()
            .should("have.class" , "new-todo")
    })

    it.only("",()=>{



        cy.get()
        .cy.type("my-name")
    })


})

```

cypress uses Mocka under the hood

### stub the network :

cy.route("GET" , "/api/todos" , [{}])

```javascript
// add todos.json to the fixtures folder

cy.fixture("todos").then();
//or
cy.route("GET", "/api/todos/", "fixture:todos").as("wait-name");
cy.wait("@wait-name");
```

```javascript
// support/commands.js

Cypress.Commands.add("seedAndVisit", () => {
  cy.server();
  cy.route("GET", "/api/todos", "fixture:todos").as("api-call");

  cy.visit();
  cy.wait("@api-call");
});

// USAGE :
cy.seedAndVisit();
```

```javascript

cy.route({
    method:"POST",
    url:'/api/todos'
    response:{id:123 , name:newTodo , isComplete:false}
}).as("save")


cy.seedAndVisit()

cy.get(".div")
.type(newTodo)
.type("{enter}")


cy.wait("@save")
cy.get(".todo li ")
.should("have.length" , 5)


```

```javascript
cy.get(".list li")
  .first()
  .find(".delete-btn")
  .invoke("show") // element is not visible display:none

  .click(); // click({force:true})
```

```js
cy.get(".todos li").as("the-list");
// usage :
cy.get("@the-list");

//Cypress._ ===> lodesh default in cypress
```

### integration test

```js
// json-server

const jsonServer = require("json-server");
const server = jsonServer().create();
const router = jsonServer().router("db.json");
const middleware = jsonServer.defaults({
  static: "./build",
});

server.use(middleware);
server.use(jsonServer.bodyParser);

server.delete("/posts/all", (req, res) => {
  router.db.setState((todos: [])).then((res) => res.sendStatus(200));
});

server.use(
  jsonServer.rewriter({
    "/api/*": "/$1",
  })
);

// what is context !!!!
context("no todo ", () => {});
```

```js
cy.get(".list li ").each(($el) => {
  cy.wrap($el).find(".delete-btn").invoke("show").click();
});
```

## another site source of learning visit : [github](github.com/brettshollenberger/cypress-egghead-course.git) !

#### cypress plugin

```js
//index.js

module.exports = (on, config) => {
  on("task"),
    {
      hello({ name }) {
        console.log(name);
        return null;
      },
    };
};
```

### kentcdodds

see this site [github](github.com/kentcdodds/testing-node-apps)
