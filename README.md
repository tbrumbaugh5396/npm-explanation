# npm-explanation
The purpose of this project is to explain the uses and how to use npm (node package manager).

## This repository is in progress.

# What is Node?
Node.js is a JavaScript runtime for building server-side or desktop applications.

## JavaScript and Node.js
Javascript has existed since 1995 and has since taken over as the dominant language for web development. 
For much of its life, JavaScript was used mainly for client-side scripting inside <script> tags executing in web browsers. 
This limitation meant that developers were often working in many different languages and frameworks between the front-end (client-side) and backend (server-side) aspects of a web application.

Although there were other projects to bring JavaScript to server-side applications, the functionality took off with the launch of Node.js in 2009. 
Node allows developers to write JavaScript code that runs directly in a computer process itself instead of in a browser. N
ode can, therefore, be used to write server-side applications with access to the operating system, file system, and everything else required to build fully-functional applications.
Node.js is written in C, C++, and JavaScript, and it is built on the open-source V8 JavaScript engine which also powers JS in browsers such as Google Chrome.
As V8 supports new features in JavaScript, they are incorporated into Node.

# What is NPM?
NPM is the world's largest Software Registry.
It is used to manage different Javscript packages and comes with Node.js
The registry contains over 800,000 code packages.
Open-source developers use npm to share software.
Many organizations also use npm to manage private development.

# How to install NPM
I am going to install npm using NixOS by installing Node.
This is in opposition to using NVM (node version manager).
NVM is a software that manages your different node installation but NixOS already allows for this so it is in conflict.

I have added nodejs_20 to my configuration.nix

# What are the commands for Node?

Accoding to: https://www.codecademy.com/article/what-is-node

## Node-Specific Functionality
### Globals

Node provides access to several important global objects for use with Node program files. 
When writing a file that will run in a Node environment, these variables will be accessible in the global scope of your file.
- module is an object referring to the functionality that will be exported from a file.
  In Node, each file is treated as a module.
- require() is a function used to import modules from other files or Node packages.
- process is an object referencing to the actual computer process running a Node program and allows for access to command-line arguments and much more.

#### Modules

Node has a many built-in modules to aid in interactions with the command line, the computer file system, and the Internet. 
These include:
- HTTP and HTTPS for creating web servers.
- File System, OS, and Path for interacting with the file system, operating system, and file/directory paths.

You can view the full docs to see more of Node’s built-in features.

According to: https://nodesource.com/blog/an-absolute-beginners-guide-to-using-npm/

### package.json
As a general rule, any project that's using Node.js will need to have a package.json file.

#### What is a package.json file?
A package.json file can be described as a manifest of your project that includes the packages and applications it depends on, information about its unique source control, and specific metadata like the project's name, description, and author.

Example package.json:
'''{
  "name": "metaverse", // The name of your project
  "version": "0.92.12", // The version of your project
  "description": "The Metaverse virtual reality. The final outcome of all virtual worlds, augmented reality, and the Internet.", // The description of your project
  "main": "index.js"
  "license": "MIT" // The license of your project
}'''

# What are the commands for NPM?
NPM initalize will help initial a node project for you with the appropriate package.json information using the command:
- npm init

You can initalize quickly with default values using the command:
- npm init --yes

package.json also contains the package dependancies and developer dependancies for a project.
Therefore, we do not need to (or shouldn't) bundle our dependancies with our project.
The versions of these packages are specified via semantic versioning.

## What is semantic versioning:
Checkout this link to learn more about semantic versioning or SemVer: https://nodesource.com/blog/semver-a-primer/
-------------------------------------------------------------------------------------------------------------------------

You can install all of these dependancies once in your project and get all the dependancies listed in you package.json using the command:
- npm install or npm i (for short)

You can install a specific module using the command:
- npm install <module> or npm i <module> (for short)

If you want to install the specific module to your package.json add the option --save to the install using the command:
- npm install <module> --save

If you want to install the specific module under the devDependancies in your package.json add the option --save-dev to install using the command:
- npm install <module> --save-dev

Often times, we want the module that we are installing to be available everywhere (rather than locally) using npm so we add the option --global to install using the command:
- npm install <module> --global

There are more available here: https://nodesource.com/blog/eleven-npm-tricks-that-will-knock-your-wombat-socks-off

## Added npm packages:
Here are a list of npm packages that I have added to my personal machine:
- meta-git (npm install meta-git --global)

NPM is locked from global installations in NixOS because the NixOS packages's filesystem is read-only.
Therefore, you have to Nixify your installation: http://nicknovitski.com/nix-npm-install
However, I am using NixOS so this can be done by adding the following line to configuration.nix:
- nodePackages.typescript

However, I can't find meta-git this way so I will continue to find a way to install it globally.
