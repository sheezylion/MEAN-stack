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









