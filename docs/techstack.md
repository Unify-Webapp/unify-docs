# Tech Stack

Now I would've separated the stack into "Frontend" and "Backend", but as we're using a **serverless** architecture, that isn't super necessary, as you may need to get your hands on the *backend* when writing code to render dynamic data to pages.

- **NextJS** : A framework built on Top of React, which provides ton of cool features like easy page routing, image compression, optimised routing to pages and much more. We use the "pages" router, NOT app router. See [this](https://medium.com/@CraftedX/should-you-use-next-js-pages-or-app-directory-38e803fe5cb4) for more context about pages vs app router.
- **React** : A frontend library to create reusable, dynamic and interactive UI components.
- **Tailwind CSS**: A CSS framework that It allows us to write CSS without every leaving our HTML.
- **TypeScript**: A language that is essentially a type-strict version of JavaScript. You will hate it at the start, but you will love it afterwards.
- **Firebase** : A serverless suite of tools provided by google which essentially makes up the **backend** of our webapp. Here's the functionalities of firebase we're using:
    - **Firestore**: A noSQL database software.
    - **Firebase Auth**: Handles authentication of users. We can use it to set up Sign Ins using social media accounts too.
    - **Firebase-Stripe-Extension**: An extension that allows us to interact with Stripe by interacting with our Firestore database, instead of directly using Stripe API's methods.
        - Add the moment, whike this is set up in our app, it is redundant and we don't use it (as of 8th Dec 2024), as we don't sell our own products yet. Instead, we have clubs sell tickets and memberships, which requires the use of Connected accounts, which is why we use the Stripe API directly.
- **Stripe**: A payment processing platform that allows us to handle payments for our webapp. We use it to handle payments for memberships and event tickets.

## Linting and formatting

- **Prettier**: A tool to format the code to ensure it looks consistent and appealing in all files. You can run `yarn lint:fix` to run Prettier through all files. Also be sure to turn "format on save" and select Prettier as the formatter on VS Code.
- **ES Lint**: A tool to impose rules (such as no semicolons) to reduce bugs and ensure our codebase is consistent across different files.
