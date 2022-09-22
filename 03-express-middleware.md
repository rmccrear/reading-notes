
# es6 Classes

Classes are templates for creating objects.
In previous times, functions and var declarations are hoisted. This means that function declarations are moved to the top of thier scope. You can use them before they are declared.
Var declarations are also hoisted (but the assigment will not).

Const and let, along with class are also hoisted, but this is to prevent you from using them before they are declared.
If you use a class, const, or let you will get a reference error if you attempt to reference it before it is declared.

Class constructors are called when the class is instantiated. One thing they can do is initialize variables. 
They can store their values on an object called "this" which represents the instantiated object.

# Express Routing

To create a route in Express, you use a _route method_. The method may be one of the HTTP verbs, such as GET, PUT, POST, and DELETE.
The first argument to the route method is a _route path_. The route path represents the path that URL will take to access the resource.
The route path has a special format that includes a :param to indicate that that part of the route will be captured and passed to the route method's
function on the request argument. The route path can use some of the syntax of regular expressions such as *, ?, +, and ().

The functions that a route method can take are callbacks that take (request, response, next) or (request, response).
If next() is called in the function it behaves as middleware and passes control on the the next callback function 
according to the routes that you have set up.

# Router

express.router() can help us modularize are routes. We can group related routes under a Router and then add them to the main app with app.user(myRoutes).

Middleware can be applied to all the routes group togehter under the Route.
