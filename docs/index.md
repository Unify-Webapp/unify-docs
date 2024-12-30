# Getting Started

Last updated: **08-12-2024**

## What is Unify?

Unify is a web app for University clubs to manage events, memberships, and ticket sales. This documentation helps new developers get started and serves as a reference.

## Setting Up Development Environment

### Requirements

- **VS Code** (recommended)
- **Node.js v18**: [Install instructions](https://nodejs.org/en/download). (Choose the right version!)
- **Yarn**: a [Package manager](https://www.youtube.com/watch?v=GTC1XhYixHs) for Node.js. Install it using `npm install -g yarn`
- **Firebase-tools**: `npm install -g firebase-tools`
- **Java v8+**: [Install instructions](https://www.oracle.com/java/technologies/downloads/).
    - I had to install `openjdk-17-jdk` on for Firebase emulator to work fine.

### Cloning the Project

1. Clone the repo: `git clone https://github.com/Unify-Webapp/Unify-app/`
2. Add `.env.development` file to the project root.
3. Install dependencies: `yarn` or `yarn install`
4. Run the dev environment: `yarn dev`
    - For emulator suite: `yarn dev:emu` (useful for testing Firebase functions locally)
5. Changes to the frontend auto-refresh the page.
