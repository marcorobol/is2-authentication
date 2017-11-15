# Node Token Authentication

This is a starting point to demonstrate the method of authentication by verifying a token using Express route middleware.
Code taken from scotch.io tutorial at https://scotch.io/tutorials/authenticate-a-node-js-api-with-json-web-tokens.

## Requirements

- node and npm

## Usage

1. Clone the repository
2. Install dependencies: `npm install`
3. Change SECRET in `config.js`
4. Add your own MongoDB database to `config.js`
5. Start the server: `node server.js`
6. Create sample user by visiting: `/setup`
7. Open the client in docs/index.html (it is also served as github pages)

### Getting a Token

Send a `POST` request to `http://localhost:8080/api/authenticate` with test user parameters as `x-www-form-urlencoded`. 

```
  {
    name: 'Nick Cerminara',
    password: 'password'
  }
```

### Verifying a Token and Listing Users

Send a `GET` request to `http://localhost:8080/api/users` with a header parameter of `x-access-token` and the token.

You can also send the token as a URL parameter: `http://localhost:8080/api/users?token=YOUR_TOKEN_HERE`

Or you can send the token as a POST parameter of `token`.
