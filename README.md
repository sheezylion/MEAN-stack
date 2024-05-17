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

Step 1: 

Launch a Virtual Server with Ubuntu Server OS
Sign in to the AWS Management Console
To get started, sign in to the AWS Management Console using your AWS account credentials. If you don’t have an AWS account, you can create one easily by following the instructions on the AWS website.

Open the EC2 Console Once you are signed in to the AWS Management Console
Search for “EC2” in the services search bar and click on “EC2” from the search results. This will open the EC2 console, where you can manage your instances.
