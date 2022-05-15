# Ello - Full Stack Engineer Coding Challenge
This is my submission to the ello-coding challenge for the fullstack position. My solution uses vuejs and vue apollo to query the provided api

```javascript
// HTTP connection to the API
const httpLink = createHttpLink({
  // You should use an absolute URL here
  uri: 'https://fullstack-engineer-test-n4ouilzfna-uc.a.run.app/graphql',
})
// Cache implementation
const cache = new InMemoryCache()
// Create the apollo client
const apolloClient = new ApolloClient({
  link: httpLink,
  cache,
})

Vue.use(VueApollo)
const apolloProvider = new VueApollo({
  defaultClient: apolloClient,
})
```
## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

