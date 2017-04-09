react-apollo-koa-example
========================

An example app using React, Apollo and Koa.

Setup
=====


Install [Node.js](https://nodejs.org/).

```sh
% npm install
```

Copy `.env.default` to `.env` and edit it.

Copy `config-default.json` to `config.json` and edit it.

Usage
=====

Launch the server:

```sh
% npm run server
```

Launch the development web server which serves the static client-side files:

```sh
% npm start
```

Open the URL (e.g. `http://localhost:3000`) in your browser.

Frameworks/Libraries
====================

### Client-side

* [React](https://facebook.github.io/react/)
* [Redux](http://redux.js.org/)
* [react-router](https://github.com/ReactTraining/react-router) and
  [react-router-redux](https://github.com/reactjs/react-router-redux) (URL routes management)
* [redux-auth-wrapper](https://github.com/mjrussell/redux-auth-wrapper) (Authentication)
* [redux-logic](https://github.com/jeffbski/redux-logic) w/ [RxJS](https://github.com/ReactiveX/rxjs)
  (Async logic management)
* [react-app-rewired](https://github.com/timarney/react-app-rewired)
  (Customizing create-react-app w/o ejection)
* [Apollo](http://dev.apollodata.com/) (GraphQL)
* [Semantic-UI-React](http://react.semantic-ui.com/) (CSS framework)

The application code was generated by create-react-app.

See package.json for more information.

### Server-side

* [koa v.2](https://github.com/koajs/koa)
* [Apollo](http://dev.apollodata.com/) (GraphQL)

See package.json for more information.

GraphQL/Apollo
==============

Persisted Queries
-----------------

GraphQL querires, mutations and subscriptions are defined in `src/graphql` as `.graphql` files.
They can be used as persisted queries.

You can enable persisted queries by modifying `config.json`.

```json
{
    "persistedQueries": true
}
```

You need to generate `extracted_queries.json` by executing this.

```
% npm run persistgraphql
```

Read the following article to know about persisted queries.

* [Persisted GraphQL Queries with Apollo Client](https://dev-blog.apollodata.com/persisted-graphql-queries-with-apollo-client-119fd7e6bba5#.wnzn2qlpf)

Subscriptions
-------------

This example project uses subscriptions.
Select "GraphQL Subscription" tab in the header to see it.

It has not been integrated with authentication.

Read the following article to know about subscriptions.

* [A proposal for GraphQL subscriptions](https://dev-blog.apollodata.com/a-proposal-for-graphql-subscriptions-1d89b1934c18#.vso7t15e5)
