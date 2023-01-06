# Markdown Blog Example

This creates a markdown website using node.js, express and MongoDB.

This is taken from the "Web Dev Simplified - How to Build A Markdown Blog Using Node.js, Express and MongoDB" YouTube video: https://www.youtube.com/watch?v=1NrHkjlWVhM

## Technology Stack

| Technology | Version |
|------------|---------|
| Ubuntu Linux | 20.04 Focal Fossa |
| node.js | v18.12.1 |
| npm | 8.19.2 |
| MongoDB | v6.0.3 |

## NPM Modules

| Module | Version |
|--------|---------|
| dompurify | ^2.4.1 |
| ejs | ^3.1.8 |
| express | ^4.18.2 |
| jsdom | ^20.0.3 |
| marked | ^4.2.5 |
| method-override | ^3.0.0 |
| mongoose | ^6.8.2 |
| slugify | ^1.6.5 |

## Installation

### Node.js

To install node.js, it is best to use the Node Version Manager. The versions of Node.js and NPM installed with Ubuntu 20.04 are too old and throw many, many errors when installing modules:

    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

    source ~/.bashrc

    nvm install v18.12.1

### MongoDB

To install MongoDB do:

    wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc \
     | gpg --dearmor | sudo tee /usr/share/keyrings/mongodb.gpg > /dev/null

    echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb.gpg ] \
     https://repo.mongodb.org/apt/ubuntu \
     focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list

    sudo apt install mongodb-org -y

    sudo systemctl enable mongod

    sudo systemctl start mongod

### Setting Up The Environment

Create the directory we wish to use for the blog:

    mkdir markdown-blog

To initialise NPM do:

    cd markdown-blog
    npm init -y

To install the required NPM modules do:

    npm i dompurify	ejs	express	jsdom marked method-override mongoose slugify

To install the nodemon dev dependency do:

    npm i --save-dev nodemon

To configure nodemon as the startup script, edit the package.json file and under the "scripts" section, delete any existing script definitions and add:

    "devStart": "nodemon server.js"

## Server startup

To start the node.js server, do:

    npm run devStart

## Accessing the Blog

Navigate in your browser to:

    http://localhost:4000
