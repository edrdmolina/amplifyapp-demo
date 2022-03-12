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
- [Install the Amplify CLI](#2-1)
- [Configure the Amplify CLI](#2-2)
- [Initialize the Amplify app](#2-3)

3- Add Authentication
- [Install the Amplify Libraries](#3-1)
- [Create the authentication service](#3-2)
- [Deploy the authentication service](#3-3)
- [Configure the React project with Amplify resources](#3-4)
- [Add the authentication flow in App.js](#3-5)
- [Run the app locally](#3-6)
- [Set up the CI/CD of the front-end and backend](#3-7)
- [Deploy the changes to the live environment](#3-8)

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

<h2 id="2-1">Install the Amplify CLI</h2>

---
The Amplify Command Line Interface (CLI) is a unified toolchain to create AWS cloud services for your app, following a simple guided workflow. Let’s go ahead and install the Amplify CLI using the Command Prompt (Windows) or the Terminal (macOS). NOTE: this command can be run in any directory in your Command Prompt/Terminal as the “-g” indicates the binary will be installed globally on your system.

<br>

    npm install -g @aws-amplify/cli 

<br>

<h2 id="2-2">Configure the Amplify CLI</h2>

---
Amazon IAM (Identity and Access Management) enables you to manage users and user permissions in AWS. The CLI uses IAM to create and manage services programmatically on your behalf via the CLI.

To configure the CLI, run the configure command. To see a video walkthrough of the CLI configuration process, click [here](https://www.youtube.com/watch?v=fWbM5DLh25U)

<br>

    amplify configure

<br>

<h2 id="2-3">Initialize the Amplify app</h2>

---
Next, we will deploy a back end and initialize the backend environment locally.

<br>

a. In the Amplify console, click on Backend environments and click on click on <strong>Get started</strong>. Wait for the back end to be deployed.

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/react-app-module-two-1.a7a43134f5fa2f89ad63519e2e560485ae8a37ae.png" />

<br>

b. In the Backend environment tab, click on <strong>Open admin UI</strong>

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/react-app-module-two-2.cc76c109468627898d77bf59e4614fc87a8d1e5d.png" />

<br>

c. Go back to the Amplify Console Backend environments tab and open the <strong>Local setup instructions</strong>. Copy the command to your clipboard and open the terminal on your computer.

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/react-app-module-two-3.b7b745c4ff7a668cf3253ebae965b43ad668a3a9.png" />

<br>

d. Paste the command into your terminal and follow the setup instructions.

<br>

    ? Choose your default editor: Visual Studio Code
    ? Choose the type of app that you're building javascript
    ? What javascript framework are you using react
    ? Source Directory Path:  src 
    ? Distribution Directory Path: build
    ? Build Command:  npm run-script build
    ? Start Command: npm run-script start
    ? Do you plan on modifying this backend? Y

<br>

<h2 id="3-1">Install the Amplify libraries</h2>

---
We will be needing 2 Amplify libraries for our project. The main <strong>aws-amplify library</strong> contains all of the client-side APIs for interacting with the various AWS services we will be working with and the <strong>@aws-amplify/ui-react library</strong> contains framework-specific UI components. Please install these libraries in the root of the project.

<br>

    npm install aws-amplify @aws-amplify/ui-react

<br>

<h2 id="3-2">Create the authentication service</h2>

---
To create the authentication service, use the Amplify CLI:

<br>

    amplify add auth

    ? Do you want to use the default authentication and security configuration? Default configuration
    ? How do you want users to be able to sign in? Username
    ? Do you want to configure advanced settings? No, I am done.

<br>

<h2 id="3-3">Deploy the authentication service</h2>

---
Now that the authentication service has been configured locally, we can deploy it by running the Amplify push command:

<br>

    amplify push -y

<br>

<h2 id="3-4">Configure the React project with Amplify resources</h2>

---
The CLI has created and will continue to update a file called aws-exports.js located in the src directory of our project. We will use this file to let the React project know about the different AWS resources that are available in our Amplify project.

To configure our app with these resources, <strong>open src/index.js</strong> and add the following code below the last import:

<br>

    import { Amplify } from 'aws-amplify';
    import config from './aws-exports';
    Amplify.configure(config);

<br>

<h2 id="3-5">Add the authentication flow in App.js</h2>

---
Next, <strong>open src/App.js</strong> and update with the following code:

[Amplify UI Quick Start](https://ui.docs.amplify.aws/components/authenticator?platform=react#quick-start)

<br>

    import React from 'react';
    import logo from './logo.svg';
    import './App.css';
    import { Authenticator } from '@aws-amplify/ui-react';
    import '@aws-amplify/ui-react/styles.css';

    function App() {
    return (
        <Authenticator>
            {({ signOut, user }) => (
                <main>
                    <h1>Hello {user.username}</h1>
                    <button onClick={signOut}>Sign out</button>
                </main>
            )}
        </Authenticator>
    );
    }

    export default App;

<br>

<h2 id="3-6">Run the app locally<h2>

---
Next, run the app to see the new Authentication flow protecting the app:

<br>

    npm start

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20Sign%20In%20Screen%20Module%203.dc66e4d98879ec9b68577be8b0909683141f187e.png" />

<br>

Here, you can try signing up which will then automatically sign you in. When signed in, you should be see a sign out button that will sign the user out and restart the authentication flow.

<br>

<h2 id="3-7">Set up CI/CD of the front-end and backend</h2>

---
Next, we need to configure the Amplify build process to add the backend as part of the continuous deployment workflow. From your terminal window run:

<br>

    amplify console

<br>

This will open the Amplify Console inside AWS. From the navigation sidebar, choose <strong>App settings > Build settings</strong> and modify it to add the <strong>backend section (lines 2-7 in the code below)</strong> to your amplify.yml. After making the edits, choose <strong>Save</strong>.

<br>

    version: 1
    backend:
    phases:
        build:
        commands:
            - '# Execute Amplify CLI with the helper script'
            - amplifyPush --simple
    frontend:
    phases:
        preBuild:
        commands:
            - yarn install
        build:
        commands:
            - yarn run build
    artifacts:
        baseDirectory: build
        files:
        - '**/*'
    cache:
        paths:
        - node_modules/**/*

<br>

Next, update your front end branch to point to the backend environment you just created. Under the branch name, choose <strong>Edit</strong>, and then point your <strong>master</strong> branch to the <strong>dev</strong> backend you just created. Choose <strong>Save</strong>.

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20React%20-%20New%20Module3%20-%201.3217ceb655edf6eb523da92d50cf9d95580cf40c.png" />

<br>

<img src="https://d1.awsstatic.com/webteam/getting_started/GSRC%202020%20updates/Front%20End/Front%20End%20React%20-%20New%20Module3%20-%202.879da73c11bf6b7af1c481496e1a2eb1fd678e91.png" />

<br>

<h2 id="3-8">Deploy the changes to the live environment</h2>

---
Now head back to your local terminal window and deploy the changes to GitHub to kick off a new build in the Amplify console:

<br>

    git add .
    git commit -m “added auth”
    git push origin master

<br>