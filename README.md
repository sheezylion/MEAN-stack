# MEAN stack deployment to ubuntu in AWS

![1690120721509](https://github.com/sheezylion/MEAN-stack/assets/142250556/afa13788-40bc-43e1-99c4-5ae882e01531)

## Introduction to MEAN Stack

MEAN Stack is one of the most popular Technology Stack. It is used to develop a Full Stack Web Application. Although it is a Stack of different technologies, all of these are based on JavaScript language.

MEAN Stands for:

M – MongoDB

- MongoDB is an open source, NoSQL database designed for cloud applications. It uses object-oriented organization instead of a relational model.
In the MEAN stack, MongoDB stores the application’s data. Because both the application and the database use JavaScript, there’s no need to translate the object as it journeys from the application to the database and back.
The application can push and pull objects between the back end and the database without missing a beat.

E – Express
- Express is a web application framework for Node.js. It balances ease of use and a full feature set.
Forming the back end of the MEAN stack, Express handles all the interactions between the front end and the database, enabling a smooth transfer of data to the user.
It’s designed to be used with Node.js and to continue the consistent use of JavaScript throughout the stack.

A – AngularJS
- AngularJS—Google’s JavaScript front end framework—isn’t the only front end framework in use, but it’s exceedingly popular.
It is effectively the default for front end JavaScript development. If you’re developing a web application in JavaScript, you’re using AngularJS.
The MEAN stack includes AngularJS to help developers build the user-facing side of the application.
Because the back end, front end and database are all built on JavaScript, there’s a smooth flow of information between all parts of your application.

N – Node.js
- Node.js is the backbone of the MEAN stack. Express is purpose-built to work on top of Node.js and AngularJS connects seamlessly to Node.js for fast data serving.
Node.js comes complete with an integrated web server, making it easy to deploy your MongoDB database and application to the cloud.

MEAN stack leads to faster development as well as the deployment of the Web Application. Angular is Frontend Development Framework whereas Node.js, Express, and MongoDB are used for Backend development.

## MEAN stack use cases
While the MEAN stack isn’t perfect for every application, there are many uses where it excels. 
It’s a strong choice for developing cloud-native applications because of its scalability and its ability to manage concurrent users. 
The AngularJS front end framework also makes it ideal for developing single-page applications (SPAs) that serve all information and functionality on a single page. 

#### Here are a few examples for using MEAN:

- Calendars
- Expense tracking
- News aggregation sites
- Mapping and location finding

### Prerequisites
Have an AWS account set up and have an Admin user created with full admin permissions.

1. Launch a Virtual Server with Ubuntu Server OS
Sign in to the AWS Management Console
To get started, sign in to the AWS Management Console using your AWS account credentials. If you don’t have an AWS account, you can create one easily by following the instructions on the AWS website.

Open the EC2 Console Once you are signed in to the AWS Management Console
Search for “EC2” in the services search bar and click on “EC2” from the search results. This will open the EC2 console, where you can manage your instances.

<img width="1055" alt="Screenshot 2024-05-17 at 17 44 43" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/b5b22f79-369c-49c3-bc29-c727c9eab823">

2. Click on the “Launch Instance” button.

<img width="706" alt="Screenshot 2024-05-17 at 17 46 10" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/eee86c49-8ad0-4d0c-9aef-4a584e7b4cb2">

3. Provide a name and tags for your EC2 instance.

<img width="813" alt="Screenshot 2024-05-17 at 17 48 14" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/a2794982-6c07-471c-8f85-7b873211e9e9">

4. Choose an Amazon Machine Image (AMI), which is the operating system and software that will run on your instance.
It is recommended to choose the default option that is free-tier eligible. In this documentation we would select ubuntu server 24.04 LTS

<img width="814" alt="Screenshot 2024-05-17 at 17 49 37" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/2d0eb12c-10eb-4d73-808d-9297d551bb4a">

5. Select an instance type, determining the hardware configuration based on your resource requirements. We would select t2.nano family for this documentation

<img width="843" alt="Screenshot 2024-05-17 at 17 51 53" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/307dea53-56eb-4ae4-a5b3-ba9304602082">

6. Create a Key Pair
To securely access your EC2 instance from your system, you need to create a key pair. A key pair consists of a public key that AWS stores and a private key that you download to your local machine. The private key is used to authenticate and establish a secure connection with your EC2 instance.

You have the option to select an existing key pair if you already have one, or you can create a new key pair by clicking on the “Create new key pair” button. I already have an existing key pair created

<img width="815" alt="Screenshot 2024-05-17 at 17 53 21" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/95e6db70-b0b9-4d89-bdd6-9d4424f19997">

7. Configure the network settings. Create a security group and allow SSH traffic and HTTP traffic from the internet.
Security groups define inbound and outbound rules for network access to your instance.

<img width="807" alt="Screenshot 2024-05-17 at 17 54 26" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/b65d9bb1-7283-401e-9d32-85f72bfc63d1">

8. Configure storage. Specify the size and type of storage (EBS volumes) you need for your instance.
It is recommended to use the default settings, which are free-tier eligible.

<img width="805" alt="Screenshot 2024-05-17 at 17 55 33" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/dd90308d-4e32-4558-b488-a079daecf61b">

9. Specify the number of instances you want to launch in the summary section. In our case we only need 1 instance. Then click on the “Launch Instance” button.

<img width="826" alt="Screenshot 2024-05-17 at 17 58 46" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/eeaa36af-aeb3-4f4a-8f27-3193768bd96a">

10. Once the instance is launched, you’ll see a success message. Scroll down and click on the “View all Instances” button.

<img width="939" alt="Screenshot 2024-05-18 at 11 32 40" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/22551888-4d39-43b8-9914-a402b5af5df1">

11. Clicking on the instance ID will take you to the EC2 Instances page, where you can see the details and manage your instances effectively.

<img width="1072" alt="Screenshot 2024-05-18 at 11 34 43" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/4cc43a36-8489-436f-aee9-6866a3b7147e">

This page provides comprehensive information about our instances, including status, instance type, public IP address, and other relevant details.

#### Connect to Instance

I will connect to this using ssh client via port 22. This is done using the following block of code:

```
ssh -i ~/Downloads/demo-pair.pem ubuntu@54.196.152.96
```
Where username=ubuntu and public ip address = 54.196.152.96

<img width="718" alt="Screenshot 2024-05-18 at 11 38 54" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/b501bbe1-5de5-4197-8420-a5b067a72cfc">

### Step 1 - Install Nodejs

Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine. Node.js is used in this tutorial to set up the Express routes and AngularJS controllers.

1. Update and Upgrade ubuntu

```
sudo apt update && sudo apt upgrade -y
```

<img width="912" alt="Screenshot 2024-05-18 at 11 41 41" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/bbd90cc9-6faa-40ef-bea2-2b86beed15a2">

2. Add certificates

```
sudo apt -y install curl dirmngr apt-transport-https lsb-release ca-certificates
```

<img width="1160" alt="Screenshot 2024-05-18 at 11 43 29" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/9a1379d9-f854-43c8-a244-1a6b1bcb0b52">

```
curl -sL https://deb.nodesource.com/setup_18.x | sudo -E bash -
```
<img width="988" alt="Screenshot 2024-05-18 at 11 44 40" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/db28a3cd-09a7-4ecc-bc35-f4a16a4e9f7b">

3. Next we install nodeJS

```
sudo apt-get install -y nodejs
```

<img width="981" alt="Screenshot 2024-05-18 at 11 45 47" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/6b5ad9c4-b415-4203-b4ab-96d0cf731d58">

### Step 2 - Install MongoDB
MongoDB is a NOSQL that stores data in flexible JSON-like documents. For our example application we are adding book
records to mongoDB that contains book name, ISBN number, Author and number of pages.

1. Download the MongoDB public GPG key

To import the MongoDB public GPG key, run the following command:

```
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
```

2. Create a list file for MongoDB
Create the /etc/apt/sources.list.d/mongodb-org-7.0.list file for Ubuntu 22.04:

```
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
```

<img width="1678" alt="Screenshot 2024-05-18 at 11 59 25" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/f85d9741-782a-4f16-b0b6-719b0b7f4d0c">

3. Reload local package database
Issue the following command to reload the local package database:

```
sudo apt-get update
```

<img width="810" alt="Screenshot 2024-05-18 at 12 00 21" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/d9da55c0-068d-4c3b-90a7-51431f4231c1">

4. Install the MongoDB packages
You can install either the latest stable version of MongoDB or a specific version of MongoDB.

```
sudo apt-get install -y mongodb-org
```

<img width="1323" alt="Screenshot 2024-05-18 at 12 02 06" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/1274ee20-6bc1-4c6e-9327-fa293469e88c">

5. Start and enable mongoDB

To start the server copy the command below:

```
sudo systemctl start mongod
```

To enable the server runs copy the command below:

```
sudo systemctl enable mongod
```

To verify the server is up and running, copy the command below:

```
sudo systemctl status mongod
```
<img width="1518" alt="Screenshot 2024-05-18 at 12 07 15" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/1a45362c-65b1-47e5-90cf-ef49cf6c1ce1">

6. Install body-parser package

Body-perser package is used to process JSON files passed in requests to the server.

```
sudo npm install body-parser
```
<img width="614" alt="Screenshot 2024-05-18 at 12 09 11" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/9db11f0e-25d2-459f-b21a-bf757da6ecb2">

7. Create a folder named books for our application and cd into the newly created folder:
  
```
mkdir Books && cd Books
```

8. In the book folder initialize using npm init

```
npm init
```

<img width="853" alt="Screenshot 2024-05-18 at 12 12 55" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/71452e21-a6f7-4013-bb6e-62f281d45992">

9. Add file named server.js to Books folder

```
vim server.js
```
Copy and paste the web server code below into the server.js file.

```
const express = require('express');
const bodyParser = require('body-parser');
const mongoose = require('mongoose'); 
const path = require('path'); 
const app = express();

// To connect to MongoDB
mongoose.connect('mongodb://localhost:27017/test', { useNewUrlParser: true, useUnifiedTopology: true })
  .then(() => console.log('MongoDB connected'))
  .catch(err => console.error('MongoDB connection error:', err));

// The middleware
app.use(bodyParser.json());
app.use(express.static(path.join(__dirname, 'public')));

// For routes
require('./apps/routes')(app);

// To start the server
app.set('port', 3300);
app.listen(app.get('port'), () => {
  console.log('Server up: http://localhost:' + app.get('port'));
});
```
<img width="870" alt="Screenshot 2024-05-18 at 12 17 45" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/b3d37492-0308-458b-9974-6405f64999e5">

### Step 3 - Install Express and set up routes to the server

ExpressJS is a flexible and minimal nodeJS web application framework which is used to provide features for web and mobile application. Hence this is why express would be used to pass information to and from our mongoDB database:

1. Install express and mongoose using the command below:

```
sudo npm install express mongoose
```

<img width="547" alt="Screenshot 2024-05-18 at 12 22 49" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/20a30426-32b8-4a85-b2e7-aae261e82517">

2. In Books folder, create a folder named ‘apps’ and cd into the apps folder

```
mkdir apps && cd apps
```

3. In the apps folder, create a file named routes.js

```
vim routes.js
```

Copy and paste the code below into routes.js

```
const Book = require('./models/book');
const path = require('path');

module.exports = function(app) {
  // Get all books
  app.get('/book', async (req, res) => {
    try {
      const books = await Book.find({});
      res.json(books);
    } catch (err) {
      console.error(err);
      res.status(500).json({ error: 'Internal Server Error' });
    }
  });

  // Add a new book
  app.post('/book', async (req, res) => {
    try {
      const book = new Book({
        name: req.body.name,
        isbn: req.body.isbn,
        author: req.body.author,
        pages: req.body.pages
      });
      const result = await book.save();
      res.json({
        message: "Successfully added book",
        book: result
      });
    } catch (err) {
      console.error(err);
      res.status(500).json({ error: 'Internal Server Error' });
    }
  });

  // Update a book
  app.put('/book/:isbn', async (req, res) => {
    try {
      const updatedBook = await Book.findOneAndUpdate(
        { isbn: req.params.isbn },
        req.body,
        { new: true }
      );
      if (!updatedBook) {
        return res.status(404).json({ error: 'Book not found' });
      }
      res.json({
        message: "Successfully updated the book",
        book: updatedBook
      });
    } catch (err) {
      console.error(err);
      res.status(500).json({ error: 'Internal Server Error' });
    }
  });

  // Delete a book
  app.delete('/book/:isbn', async (req, res) => {
    try {
      const result = await Book.findOneAndRemove({ isbn: req.params.isbn });
      if (!result) {
        return res.status(404).json({ error: 'Book not found' });
      }
      res.json({
        message: "Successfully deleted the book",
        book: result
      });
    } catch (err) {
      console.error(err);
      res.status(500).json({ error: 'Internal Server Error' });
    }
  });

  // Serve static files
  app.get('*', (req, res) => {
    res.sendFile(path.join(__dirname, '../public', 'index.html'));
  });
};
```
![Screenshot 2024-05-18 at 12 26 01](https://github.com/sheezylion/MEAN-stack/assets/142250556/35d26cff-9749-45e4-8fce-2da234ea905a)


4. In the ‘apps’ folder, create a folder named models and cd into the models folder

```
mkdir models && cd models
```

5. In models, create a file named book.js

```
vim book.js
```

Copy and paste the code below into book.js:

```
const mongoose = require('mongoose');

const bookSchema = new mongoose.Schema({
  name: { type: String, required: true },
  isbn: { type: String, required: true, unique: true },
  author: { type: String, required: true },
  pages: { type: Number, required: true }
});

module.exports = mongoose.model('Book', bookSchema);
```
<img width="538" alt="Screenshot 2024-05-18 at 12 29 43" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/f02b4e89-dc7a-4129-a4f9-c36aa8c9de0c">

### Step 4 - Access the routes with AngularJS

AngularJS provides a framework for creating dynamic views in web app;ication. In this MEAN stack documentation we use AngularJS to 
connect our webpage with express and perform actions on our book register. 

1. Change the directory back to ‘Books’ 

```
cd ../..
```

2. Create a folder named ‘public’ in the Books directory and cd inside the public folder

```
mkdir public && cd public
```
<img width="506" alt="Screenshot 2024-05-18 at 12 35 20" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/0cc3406a-b6ce-41fe-b27b-564d690f65d4">


3. Add a file named script.js into public folder

```
vim script.js
```

Copy and paste the code below (controller configuration defined) into the script.js file.

```
var app = angular.module('myApp', []);

app.controller('myCtrl', function($scope, $http) {
  // Get all books
  function getAllBooks() {
    $http({
      method: 'GET',
      url: '/book'
    }).then(function successCallback(response) {
      $scope.books = response.data;
    }, function errorCallback(response) {
      console.log('Error: ' + response.data);
    });
  }

  // Initial load of books
  getAllBooks();

  // Add a new book
  $scope.add_book = function() {
    var body = {
      name: $scope.Name,
      isbn: $scope.Isbn,
      author: $scope.Author,
      pages: $scope.Pages
    };
    $http({
      method: 'POST',
      url: '/book',
      data: body
    }).then(function successCallback(response) {
      console.log(response.data);
      getAllBooks();  // Refresh the book list
      // Clear the input fields
      $scope.Name = '';
      $scope.Isbn = '';
      $scope.Author = '';
      $scope.Pages = '';
    }, function errorCallback(response) {
      console.log('Error: ' + response.data);
    });
  };

  // Update a book
  $scope.update_book = function(book) {
    var body = {
      name: book.name,
      isbn: book.isbn,
      author: book.author,
      pages: book.pages
    };
    $http({
      method: 'PUT',
      url: '/book/' + book.isbn,
      data: body
    }).then(function successCallback(response) {
      console.log(response.data);
      getAllBooks();  // Refresh the book list
    }, function errorCallback(response) {
      console.log('Error: ' + response.data);
    });
  };

  // Delete a book
  $scope.delete_book = function(isbn) {
    $http({
      method: 'DELETE',
      url: '/book/' + isbn
    }).then(function successCallback(response) {
      console.log(response.data);
      getAllBooks();  // Refresh the book list
    }, function errorCallback(response) {
      console.log('Error: ' + response.data);
    });
  };
});
```

<img width="423" alt="Screenshot 2024-05-18 at 12 36 49" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/ba7eec12-d902-4d2a-86c4-bcf83a7c5c4e">

4.  In ‘public’ folder, create a file named index.html

```
vim index.html
```

Copy and paste the code below into index.html file:

```
<!DOCTYPE html>
<html ng-app="myApp" ng-controller="myCtrl">
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.4/angular.min.js"></script>
  <script src="script.js"></script>
</head>
<body>
  <div>
    <table>
      <tr>
        <td>Name:</td>
        <td><input type="text" ng-model="Name"></td>
      </tr>
      <tr>
        <td>Isbn:</td>
        <td><input type="text" ng-model="Isbn"></td>
      </tr>
      <tr>
        <td>Author:</td>
        <td><input type="text" ng-model="Author"></td>
      </tr>
      <tr>
        <td>Pages:</td>
        <td><input type="number" ng-model="Pages"></td>
      </tr>
    </table>
    <button ng-click="add_book()">Add</button>
    <div ng-if="successMessage">{{ successMessage }}</div>
    <div ng-if="errorMessage">{{ errorMessage }}</div>
  </div>
  <hr>
  <div>
    <table>
      <tr>
        <th>Name</th>
        <th>Isbn</th>
        <th>Author</th>
        <th>Page</th>
        <th>Action</th>
      </tr>
      <tr ng-repeat="book in books">
        <td>{{ book.name }}</td>
        <td>{{ book.isbn }}</td>
        <td>{{ book.author }}</td>
        <td>{{ book.pages }}</td>
        <td><button ng-click="del_book(book)">Delete</button></td>
      </tr>
    </table>
  </div>
</body>
</html>
```
<img width="779" alt="Screenshot 2024-05-18 at 12 40 46" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/14f6b378-28e1-4558-90bc-7140e7cf128d">

5. Change the directory back up to ‘Books’ 

```
cd ..
```

6. Start the server with the command below:

```
node server.js
```
<img width="1516" alt="Screenshot 2024-05-18 at 12 43 37" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/ba912cc2-fc62-4ed0-90a7-63f9c255fe03">

This server is now up and running as seen in the screenshot above, we can connect via port 3300.

Hence to view our Book app via the URL, we need to open TCP port 3300 in our AWS EC2 instance. Under the Security group we would
edit our inbound rules and add rules, just as shown below

<img width="1586" alt="Screenshot 2024-05-18 at 12 48 24" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/da8f3726-12fb-415c-8d05-2c2906595291">

7. The Book Register web application can now be accessed from the internet with a browser using the Public IP address or Public DNS name.

```
http://54.196.152.96:3300/
```

<img width="1560" alt="Screenshot 2024-05-18 at 12 49 48" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/f9f30608-222c-48a3-9bb4-0cea3b34d7a8">

Input details into the book application 

<img width="812" alt="Screenshot 2024-05-18 at 12 53 24" src="https://github.com/sheezylion/MEAN-stack/assets/142250556/a8f00064-3dbc-4716-874a-c61a56dff12e">

### Conclusion

By leveraging MongoDB for our database management, Express.js for server-side routing and middleware, AngularJS for front-end development, and Node.js for scalable server-side operations, we've crafted a book application of modern web development.





























