# json_crud
A common task for front-end developers is to simulate a backend REST service to deliver some data in JSON format to the front-end application and make sure everything is working as expected.

Of course you can setup a full backend server, e.g. by using Node.js, Express and MongoDB. However this takes some time and a much simpler approach can help to speed up front-end development time. 

JSON Server is a simple project that helps you to setup a REST API with CRUD operations very fast. The project website can be found at https://github.com/typicode/json-server.

In the following you’ll lean how to setup JSON server and publish a sample REST API. Furthermore you’ll see how to use another library, Faker.js, to generate fake data for the REST API which is exposed by using JSON server.
Installing JSON Server
JSON Server is available as a NPM package. The installation can be done by using the Node.js package manager:
$ npm install -g json-server
By adding the -g option we make sure that the package is installed globally on your system.
JSON File
Now let’s create a new JSON file with name db.json. This file contains the data which should be exposed by the REST API. For objects contained in the JSON structure CRUD entpoints are created automatically. Take a look at the following sample db.json file:
{
  "employees": [
    {
      "id": 1,
      "first_name": "eng",
      "last_name": "sunny",
      "email": "hyginussunny7@gmail.com"
    },
    {
      "id": 2,
      "first_name": "Steve",
      "last_name": "Palmer",
      "email": "steve@codingthesmartway.com"
    },
    {
      "id": 3,
      "first_name": "Ann",
      "last_name": "Smith",
      "email": "ann@codingthesmartway.com"
    }
  ]
}
The JSON structure consists of one employee object which has three data sets assigned. Each employee object is consisting of four properties: id, first_name, last_name and email.
Running The Server
Let’s start JSON server by executing the following command:
$ json-server --watch db.json
As a parameter we need to pass over the file containing our JSON structure (db.json). Furthermore we’re using the — watch parameter. By using this parameter we’re making sure that the server is started in watch mode which means that it watches for file changes and updates the exposed API accordingly.
Now we can open URL http://localhost:3000/employees in the browser 
Testing API Endpoints With POSTman
Initiating a GET request is easy by simply using the browser. For initiating other types of HTTP requests you can make use of an HTTP client tool like Postman (https://www.getpostman.com). Postman is available for MacOS, Windows and Linux. Furthermore Postman is available as a Chrome App.
Get Request
The Postman user interface is easy to use. To initiate a GET request fill out the form as you can see in the following screenshot. Click the Send button and you’ll receive the response in JSON format:
