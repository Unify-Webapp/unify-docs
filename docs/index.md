# Getting Started
## What is Unify?

Unify is a web application that provides a platform for University clubs for advertising themselves, publishing their events, managing memberships, ticket sales as well as a way for students to discover new clubs, events, purchasing memberships and buying event tickets.

This documentation is intended for developers of the Unify team. If you're new to the team, we're putting together this resource to help you get up to speed, and hopefully serve as a venue which you can refer to when you get stuck in some technical aspect during development.

Please feel free to contribute to this documentation so we can ensure our project is sustainable and it's easier for new developers to get on board!

## Setting Up Development Environment

Most of our developers use and recommend [VS Code](https://code.visualstudio.com/) as our code editor but you may use whatever software you choose, however note that VS Code provides very useful extensions which may or may not exist for other editors.

- Clone the repository by running: `git clone https://github.com/Unify-Webapp/Unify-app/`
- Ask your team for the .env file. Place this file in the directory your just cloned (should be named "unify-app" by default)
- Install dependencies by running: `yarn` or `yarn install`
- Run the development environment by running: `yarn dev:emu` (do **NOT** use `yarn dev` unless your really know what you're doing.)
- Now everytime you make a change to the frontend, it should refresh the page automatically.
- Some backend changes such as addition of new cloud functions will require you to restart the dev server.