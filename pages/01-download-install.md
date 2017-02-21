# Download / Install

Before you can get started you'll need to download and install some tools.

## Git / git bash

Git is a version conrol system used by basically everyone. A version control system allows you to keep a history of changes you make to an app, and most importantly makes it much easier to collaborate with others on a project.

Bash is an open source command line shell used for interacting with your computer with commands. By default windows uses CMD or PowerShell which have a slightly different language. Git Bash allows you to use bash on windows. The Mac Terminal runs bash by default so if you develop on mac in the future you'll already be used to it. Additionally, most web servers run some flavor of linux (which you'll access by connecting via ssh and using bash commands)

Download: [Git / git bash](https://git-scm.com/downloads) - version control / bash emulator

Install: Just click next with all of the default settings

## Node JS / NPM

NodeJS is a javascript run time that allows you to execute javascript code form the command line. It is commonly used for creating utility scripts and command line tools. It also enables creating web servers that run on javascript code which enables you to use the same language on the server and the client.

NPM (Node Package Manager) is the defacto package manager for javascript. For a long time it was only nodeJS / server side packages, but it has evolved to become the primary source for frontend libraries as well.

Download: [NodeJS](https://nodejs.org/en/)

Install: Just click next with all of the default settings

## Code Editor

To write code you need an editor. I recommend VS Code. Sublime Text and Atom are also great choices, but VS Code is my current favorite.

Download: [VS Code](https://code.visualstudio.com/)

Install: Just click next with all of the default settings

## Check your installation

* Open git bash - Press `WIN+S` type `gitb` select git bash
* Type `ls` - you should see a list of files in your home directory
* Type `git -v` this should load git with the version (check that it matches what you downloaded)
* Type `node -v` this should show you the nodeJS version (check that it matches what you downloaded)
* Type `npm -v` this should show you the npm version (check that it matches what you downloaded)
* Type `code` this should open VS Code with an empty document

If all of this worked you've succeeded. If not try installing anything missing again.
