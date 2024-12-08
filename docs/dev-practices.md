# Development Practices

This page documents coding patterns and best practices used in the Unify project.

## Using Stripe CLI to Develop and Test Webhooks Locally

The Stripe CLI is a handy tool to interact with the Stripe API. It is particularly useful for developing and testing webhooks locally. This section provides an overview of how to use the Stripe CLI to develop and test webhooks locally.

### Prerequisites

- A Stripe account
- Stripe CLI installed on your machine
- A local development server running (e.g., Next.js)

### Installation

#### Install Stripe CLI

To install the Stripe CLI, follow the instructions for your operating system [here](https://docs.stripe.com/stripe-cli?install-method=linux).

### Authentication

Authenticate the Stripe CLI with your Stripe account:

```sh
stripe login
```

This command will open a browser window where you can log in to your Stripe account. Once logged in, the CLI will be authenticated and linked to your Stripe account.

### Forwarding Webhooks

Use the Stripe CLI to forward webhook events to your local server. Replace `http://localhost:3000/api/stripe-webhook` with your local endpoint:

```sh
stripe listen --forward-to http://localhost:3000/api/stripe-webhook
```

This command will start listening for Stripe events and forward them to your local endpoint.

### Triggering Test Events

You can trigger test events using the Stripe CLI. For example, to trigger a `checkout.session.completed` event, run:

```sh
stripe trigger checkout.session.completed
```

This will send a test event to your local webhook endpoint, allowing you to test your webhook handler.

### Webhook Handler & Checkout API Endpoint

The Stripe aspect of the Unify project requires two api endpoints:

- **Checkout API Endpoint**: Initiates and customizes the checkout process, handling secure payments and order tracking.
- **Webhook Handler**: Manages real-time updates and automated actions from Stripe events.
    - We perform the fee-deduction logic here as well.

#### How They Work Together

1. **User Checkout**: User initiates a purchase, triggering the checkout API endpoint.
2. **Create Session**: The endpoint creates a checkout session with Stripe and redirects the user to Stripe's checkout page.
3. **Complete Payment**: User completes payment on Stripe's page.
4. **Receive Notification**: Stripe sends a `checkout.session.completed` event to the webhook handler.
5. **Process Event**: The webhook handler updates order status, captures payment, and sends confirmation emails.
6. **Fulfill Order**: Your application proceeds with order fulfillment.

### Common Issues

#### Missing Metadata

When using the Stripe CLI to trigger events, the generated events may not include all the custom metadata fields you set in your actual application. Ensure your webhook handler handles the absence of these fields gracefully.

#### API Key Permissions

When using Stripe CLI, you can't pass metadata (or maybe you can, I didn't have enough time to find out), hence it'll complain
that the API key is wrong even though it isn't.
Instead, hardcode an account number for testing purposes.
