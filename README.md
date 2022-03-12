# [Build a Full-Stack React Application](https://aws.amazon.com/getting-started/hands-on/build-react-app-amplify-graphql/)

This README.md file contains the step-by-step instructions on how to create a Full-Stack React application using AWS Amplify, GraphQL, DynamoDB ,and S3 storage for images.

<br>

## Table of Contents
---
1- Host React App
- [Create a new React Application](#1-1)
- [Initialize Github repository](#1-2)
- [Log into AWS Management Console](#1-3)
- [Deploy your app with AWS Amplify](#1-4)
- [Automatically deploy code changes](#1-5)

2- Initialize Local App

3- Add Authentication

4- Add API and Database

5- Add Storage

<br>

<h2 id="1-1">Create a new React Application</h2>

---
Begin by initializing a new react app with create-react-app.

If you do not have create-react-app installed globally on your machine. [Follow these instructions](https://create-react-app.dev/docs/getting-started).

<br>

    npx create-react-app amplifyapp
    cd amplifyapp
    npm start

<br>

<h2 id="1-2">Initialize a GitHub repository</h2>

---
Open your Github account and create a new repository. Then on your terminal within the amplifyapp directory connect to the repository.

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20GitHub%20Repository%20Module%201.00346ba956342a17bf7bd75ba1012c1354976147.png" />

<br>

    git init
    git remote add origin git@github.com:username/reponame.git
    git add .
    git commit -m “initial commit”
    git branch -M master
    git push origin master

<br>

<h2 id="1-3">Log into AWS Management Console</h2>

---
Open the [AWS Management Console](https://console.aws.amazon.com/console/home?region=us-east-1) in a new browser window, so you can keep this step-by-step guide open. When the screen loads, enter your user name and password to get started. Then type "Amplify" in the search bar and select AWS Amplify to open the service console.

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20AWS%20Console%20Find%20Amplify%20Module%201.47a33baea2346b85a1d4bd157b9df5bebe693c4b.png" />

<br>

<h2 id="1-4">Deploy your app with AWS Amplify</h2>

---
In this step, you will connect the GitHub repository you just created to the AWS Amplify service. This will enable you to build, deploy, and host your app on AWS.

<br>

a.  In the AWS Amplify service console, select "Get Started" under <strong>Deploy</strong>.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20Amplify%20Deploy%20Module%201.b740714a147c434a54bb08236a61065a42f461d3.PNG" />

<br>

b. Select GitHub as the repository service and select <strong>Continue</strong>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20Amplify%20GitHub%20Module%201.04ba11118824e16e3d7d418d4f211d75a4649d1e.png" />

<br>

c. Authenticate with GitHub and return to the Amplify console. Choose the repository and master branch you created earlier, then select <strong>Next</strong>.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20GitHub%20Add%20Repository%20Module%201.429417921ff6dc1d42e7926decb77178272a4449.png" />

<br>

d. Accept the default build settings and select <strong>Next</strong>.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20GitHub%20Add%20Repository2%20Module%201.b9eec627876388afd79e002c67684e0978663881.png" />

<br>

e. Review the final details and select <strong>Save and Deploy</strong>.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20GitHub%20Add%20Repository3%20Module%201.c8bbf443a50fcbcf80a00bfd6873956aa4292708.png" />

<br>

f. AWS Amplify will now build your source code and deploy your app at https://...amplifyapp.com.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20Amplify%20Deploy%20Source%20Module%201.00becc211a8ecd42349cffb87406449074ed2e5c.png" /> 

<br>

g. Once the build completes, select the thumbnail to see your web app up and running live. 

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20Initial%20App%20Module%201.ba286128748534afaa9769ca76675680a4e13047.png" />

<br>

<h2 id="1-5">Automatically deploy code changes</h2>

---
In this step, you will make some changes to the code using your text editor and push the changes to the master branch of your app.

a. Edit <strong>src/App.js</strong> with the code below and save

    import React from 'react';
    import logo from './logo.svg';
    import './App.css';

    function App() {
    return (
        <div className="App">
        <header className="App-header">
            <img src={logo} className="App-logo" alt="logo" />
            <h1>Hello from V2</h1>
        </header>
        </div>
    );
    }

    export default App;

<br>

b. Push the changes to GitHub in the Command Prompt (Windows) or Terminal (macOS) to automatically kick off a new build: 

    git add .
    git commit -m “changes for v2”
    git push origin master

<br>

c. Once the build is complete, select the thumbnail on the AWS Amplify console to view your updated app.

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20HelloV2%20App%20Module%201.3a931f5b5905e879b1f1bc1e0b5b471ac0f639f6.png" />

<br>