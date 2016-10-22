##Application
* Handle CRUD for an item (we’re going to use bears)
* Have a standard URL (http://example.com/api/bears and http://example.com/api/bears/:bear_id)
* Use the proper HTTP verbs to make it RESTful (GET, POST, PUT, and DELETE)
* Return JSON data
* Log all requests to the console

### Packages
* express is the Node framework. 
* mongoose is the ORM we will use to communicate with our MongoDB database.
* body-parser will let us pull POST content from our HTTP request so that we can do things like create a bear.
 * access :bear_id from the request
### Testing API using Postman
Postman will help us test our API. It will basically send HTTP requests to a URL of our choosing. We can even pass in parameters (which we will soon) and authentication (which we won’t need for this tutorial).
* [https://www.getpostman.com/]: Download Postman
* Send the name data as x-www-form-urlencoded. This sends all of our data to the Node server as query strings

### Database and Model
* Database: MongoDB database using mongoose to interact with our collection.
* Model: single name field

### Express Routes
| Route               | HTTP Verb     | Description               |
| ------------------- |:-------------:| -------------------------:|
| /api/bears          | GET           | Get all the bears         |
| /api/bears          | POST          | Creat a bear              |
| /api/bears/:bear_id | GET           | Get a single bear         |
| /api/bears/:bear_id | PUT           | Update bear with new info |
| /api/bears/:bear_id | DELETE        | Delete a bear             |

* use router.route() to chain together the different routes. This keeps the app clean and organized.

### Route Middleware
To declare middleware, use router.use(function()). The order of how we define the parts of our router is very important. They will run in the order that they are listed. (As of Express 4.0).

next() is used to indicate to our application that it should continue to the other routes. Without it the application would stop at this middleware without it.

Middleware Uses include validations, error reporting, extra logging for analytics, ect.

