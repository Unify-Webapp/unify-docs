# Tech Stack

We use a **serverless** architecture, so the distinction between "Frontend" and "Backend" isn't necessary.

- **NextJS**: Framework on top of React with features like easy page routing and image compression. We use the "pages" router. [More info](https://medium.com/@CraftedX/should-you-use-next-js-pages-or-app-directory-38e803fe5cb4)
- **React**: Library for creating reusable, dynamic UI components.
- **Tailwind CSS**: CSS framework for writing CSS within HTML.
- **TypeScript**: Type-strict version of JavaScript.
- **Firebase**: Serverless tools suite by Google.
    - **Firestore**: NoSQL database.
    - **Firebase Auth**: User authentication.
    - **Firebase-Stripe-Extension**: Interacts with Stripe via Firestore (currently redundant as of 08-12-2024).
- **Stripe**: Payment processing for memberships and event tickets.

## Linting and Formatting

- **Prettier**: Code formatter. Run `yarn lint:fix` to format all files. Enable "format on save" in VS Code.
- **ESLint**: Enforces coding rules to reduce bugs and ensure consistency.
