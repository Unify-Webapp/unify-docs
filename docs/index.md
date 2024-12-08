# Getting Started

Last updated: **08-12-2024**

## What is Unify?

Unify is a web application that provides a platform for University clubs for advertising themselves, publishing their events, managing memberships, ticket sales as well as a way for students to discover new clubs, events, purchasing memberships and buying event tickets.

This documentation is intended for developers of the Unify team. If you're new to the team, we're putting together this resource to help you get up to speed, and hopefully serve as a venue which you can refer to when you get stuck in some technical aspect during development.

Please feel free to contribute to this documentation so we can ensure our project is sustainable and it's easier for new developers to get on board!

## Setting Up Development Environment

### Requirements

Most of our developers use and recommend [VS Code](https://code.visualstudio.com/) as our code editor but you may use whatever software you choose, however note that VS Code provides very useful extensions which may or may not exist for other editors.

Other tools tools required:

- **Nodejs v22** (A JavaScript compiler written in C++. It let's us run outside of a browser, allowing us to create server-side applications in JavaScript.)
  - If you're on an ubuntu/debian based distro, [this site](https://github.com/nodesource/distributions) should have the instructions you need! If not, then go [here](https://nodejs.org/en/download)
- **Yarn** (A [package manager](https://www.youtube.com/watch?v=GTC1XhYixHs))
- **Firebase-tools** : After installing nodejs, run `npm install -g firebase-tools`. If you see permission issues, run it with `sudo` at the start of the command.
- **Java v8 or above** : Download it from [here](https://www.oracle.com/java/technologies/downloads/) (The JDK includes the JRE)
  - After downloading and installing Java, open terminal and run `java --version` to make sure it is properly installed. If it says "command not found", you may have issues with PATH. You need to set the path. Search up resources specific to your distro. For ubuntu/debian based os, you can check [this](https://ubuntuhandbook.org/index.php/2022/03/install-jdk-18-ubuntu/) out.

### Cloning the project + running the development environment

1. Clone the repository by running: `git clone https://github.com/Unify-Webapp/Unify-app/`
2. Ask your team for the `.env.development` file. Place this file in the directory your just cloned (should be named "unify-app" by default)
3. Install dependencies by running: `yarn` or `yarn install`
4. Run the development environment by running: `yarn dev`.
    - If you'd like to use the emulator suite, run `yarn dev:emu` instead. This will start the firestore and auth emulators. This is helpful to test the firebase functions locally, instead of having to deploy them to the cloud each time.
        - If using `yarn dev:emu`, addition of new cloud functions will require you to restart the dev server.
5. Now everytime you make a change to the frontend, it should refresh the page automatically.
