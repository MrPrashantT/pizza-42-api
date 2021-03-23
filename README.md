# Pizza 42 API

This sample API is to demonstrate the API authorization capabilities of Auth0 in the context of the Pizza 42 application. This sample is based off the [Auth0 Node (Express) Quickstart](https://auth0.com/docs/quickstart/backend/nodejs/01-authorization).

## Setup 
1. Clone this repository
2. Rename the `.env.sample` file to `.env` and replace all placeholder values with the appropriate values from your Auth0 tenant. `domain`, `audience` , `m2mClientId` and `m2mClientSecret`.
3. `npm install  `
4. `npm start`

## Functionality

The API exposes the `/api/orders` endpoint for the client application to invoke. The endpoint is protected using the `express-jwt` npm package to validate the access tokens passed to it, performing standard RS256 token validation.

This endpoint handles pizza order requests and performs the following operations:

1. Scope validation to ensure access tokens contain the `create:order` scope.
2. Check the `email_verified` claim to ensure only verified users can place orders.
3. Use the `auth0` Management API client to update the user's `app_metadata` to store order history.
