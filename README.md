# Lecture 06 Excercises

## Exercise 1 - Hello world

### Lab 1.1

- Download/use the demo graphql-demo from the demos folder.
- Run npm i
- Run the app with npm start and acces the graphQL endpoint in your browser.
Try to access the the graphQL endpoint from Postman.

### Lab 1.2

The demo app uses old versions of dependencies. Your task is to update it to use the newest versions - how do you do this smart?

### Lab 1.3

Change the demo app from JavaScript to Typescript. You can find help here <https://www.freecodecamp.org/news/how-to-use-typescript-with-graphql/>

## Exercise 2 - Using GraphiQL to explore an API

### Lab 2.1

Navigate to <https://docs.github.com/en/graphql/overview/explorer> and explore what kind of information you can get from GitHub.

1. Try an Introspective query.
    You can get help here: <https://graphql.org/learn/introspection/>
2. Use intellisense in GraphiQL to build some queries.

### Lab 2.2

Another site you may explore is the Star Wars service at <https://graphql.org/swapi-graphql>

1. Write a query that will list all films, and for each film show title and the name of all species that appear in the movie.
2. Use intellisense in GraphiQL to build some queries - you decide what you want to know.

## Exercise 3 - Define a GraphQL schema

### Lab 3.1

Define a GraphQL schema for a hotel booking system. Using this schema, it should be possible to query for available rooms and specify some properties for the required room.
And it should also be possible to book a room.
You can write this schema in any editor (you can install an extension to Visual Studio Code to get intellisence for GraphQL's SDL), but you can also use Apollo studio: <https://www.apollographql.com/docs/studio/getting-started/> they have a free plan you can us.
