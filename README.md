react-apollo-koa-example
========================

An example web app using React, Apollo (GraphQL), Koa v.2.

This project was generated by [create-react-app](https://github.com/facebookincubator/create-react-app)
and is not [eject](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md#npm-run-eject)ed.
Some settings are overwritten on runtime though.

[passport](https://github.com/yatsu/react-apollo-koa-example/tree/passport)
branch uses [Passport](http://passportjs.org/) to integrate authentication with
social services such as Google+, Facebook, etc., whereas `master` branch uses
[simple-oauth2](https://github.com/lelylan/simple-oauth2) to authenticate with
GitHub.

![screen image](https://raw.githubusercontent.com/yatsu/react-apollo-koa-example/master/docs/screen.png)

Setup
=====

Install [Node.js](https://nodejs.org/) and [Yarn](https://yarnpkg.com/).

Install required packages.

```sh
% yarn
```

Copy `.env.default` to `.env` and edit it to change server-side settings.

Copy `config-default.json` to `config.json` and edit it to change client-side
settings.

Usage
=====

Launch the API server:

```sh
% yarn run server
```

Launch the development web server which serves the static client-side files:

```sh
% yarn start
```

Open the URL (default: `http://localhost:3000`) in your browser.

Frameworks/Libraries
====================

### Client-side

* [React](https://facebook.github.io/react/)
* [Redux](http://redux.js.org/)
* [react-router](https://github.com/ReactTraining/react-router) and
  [react-router-redux](https://github.com/reactjs/react-router-redux)
  (URL routes management)
* [redux-auth-wrapper](https://github.com/mjrussell/redux-auth-wrapper)
  and [simple-oauth2](https://github.com/lelylan/simple-oauth2)
  (Authentication)
* [redux-logic](https://github.com/jeffbski/redux-logic)
  with [RxJS](https://github.com/ReactiveX/rxjs)
  (Async logic management)
* [react-app-rewired](https://github.com/timarney/react-app-rewired)
  (Customizing create-react-app w/o ejection)
* [Apollo](http://dev.apollodata.com/) (GraphQL)
* [Semantic-UI-React](http://react.semantic-ui.com/) (CSS framework)
* [React Storybook](https://github.com/storybooks/react-storybook) and
  [StoryShots](https://github.com/storybooks/storyshots) (UI dev and test)

The application code was generated by create-react-app.

See package.json for more information.

### Server-side (the API server)

* [Koa v.2](https://github.com/koajs/koa)
* [Apollo](http://dev.apollodata.com/) (GraphQL)

See package.json for more information.

The API server does not use DB and stores data on memory.
All changes will be cleared when you stop the server.

### Tests

* [Jest](https://facebook.github.io/jest/)
* [Nightmare](http://www.nightmarejs.org/) (Browser automation)

### Repo and code management

* [Husky](https://github.com/typicode/husky) and
  [lint-staged](https://github.com/okonet/lint-staged) (Git hooks)
* [ESLint](http://eslint.org/) with
  [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
  and our custom rules (JavaScript lint)
* [Flow](https://flow.org/) and
  [flow-typed](https://github.com/flowtype/flow-typed) (JavaScript type check)
* [prettier-eslint](https://github.com/prettier/prettier-eslint)
  (JavaScript format)
* [stylelint](https://github.com/stylelint/stylelint) with
  [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)
  (CSS lint)
* [stylefmt](https://github.com/morishitter/stylefmt) (CSS format)

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

```sh
% yarn run persistgraphql
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

Authentication
--------------

The Apollo subscription in this app is not integrated with the authentication
yet.  See the following guide to do that.

* [Authentication | Apollo Tools Guide](http://dev.apollodata.com/tools/graphql-subscriptions/authentication.html)

You might want to do it on subscribing to events instead of establishing a
connection.
See the following pull request to `subscriptions-transport-ws`.

* [onSubscribe and use middleware to modify runtime SubscriptionOptions #78](https://github.com/apollographql/subscriptions-transport-ws/pull/78)

Storybook
---------

This project uses [React Storybook](https://github.com/storybooks/react-storybook).
to develop and check presentational components.

Launch the Storybook server:

```sh
% yarn run storybook
```

[StoryShots](https://github.com/storybooks/storyshots) is also used to enable
snapshot tests.
When you modify a component and the render result is changed, Jest reports an
error. If the shown result is intended, press `u` to update the snapshot file.

Code Organization
-----------------

Redux actions, reducers and logic are managed by
[Ducks](https://github.com/erikras/ducks-modular-redux) rules in `src/ducks`
directory.

Tests are stored in `__tests__` directories under each component.

Git Hooks
---------

Git hooks are managed by [Husky](https://github.com/typicode/husky).
When you run `yarn` in this repo, Git hooks will be automatically created.

If you have a problem, you can create them manually.

```sh
% node node_modules/husky/bin/install.js
```

Our Git hooks are defined in `package.json`.
