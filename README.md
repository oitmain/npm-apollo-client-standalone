# Standalone [Apollo client](https://www.apollographql.com/client/) package for vanilla JS

## Usage

HTML

```html
<script src="https://cdn.jsdelivr.net/gh/oitmain/apollo-npm-standalone/dist/apollo.min.js"></script>
```

Javascript

```js
// import { ApolloClient } from 'apollo-client';
var ApolloClient = ApolloStandalone["apollo-client"].ApolloClient;
// import { HttpLink } from 'apollo-link-http';
var HttpLink = ApolloStandalone["apollo-link-http"].HttpLink;
// import { InMemoryCache } from 'apollo-cache-inmemory';
var InMemoryCache = ApolloStandalone["apollo-cache-inmemory"].InMemoryCache;
// import gql from 'graphql-tag';
var gql = ApolloStandalone["graphql-tag"];

var client = new ApolloClient({
  // By default, this client will send queries to the
  //  `/graphql` endpoint on the same host
  link: new HttpLink(),
  cache: new InMemoryCache()
});

var query =  gql`
    query TodoApp {
      todos {
        id
        text
        completed
      }
    }
  `;
```

## Update apollo client version

```bash
# check if new version of apollo-client is released
npm outdated
# installing up to date apollo-client
npm install --save apollo-client@{version}
# compile. files will be in ./dist folder
npm run compile
```
