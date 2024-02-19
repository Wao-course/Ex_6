# Lecture 06 Excercises

## Exercise 1 - Hello world

### Lab 1.1

- Download/use the demo graphql-demo from the demos folder.
- Run npm i
- Run the app with npm start and acces the graphQL endpoint in your browser.
- Try to access the the graphQL endpoint from Postman.

### Lab 1.2

- The demo app uses old versions of dependencies. Your task is to update it to use the newest versions - how do you do this smart?

### Lab 1.3

- Change the demo app from JavaScript to Typescript. You can find help here <https://www.freecodecamp.org/news/how-to-use-typescript-with-graphql/>

## Exercise 2 - Using GraphiQL to explore an API

### Lab 2.1

Navigate to the Star Wars service at <https://swapi-graphql.eskerda.vercel.app/>

- Write a query to get the name and eye color for the person with personId: 4.
- Write a query that will list all films, and for each film show title and the name of all species that appear in the movie.
- Use intellisense in GraphiQL to build some queries - you decide what you want to know.

## Exercise 3

### Lab 3.1

Navigate to the "Introduction to Apollo Server" at <https://www.apollographql.com/docs/apollo-server/>

- Follow the Get started tutorial by pressing the button at the botton of the page.
-- Compare the the tutorial with the slide: Apollo Server and consider pros and cons of the differences
- Read Schema basics <https://www.apollographql.com/docs/apollo-server/schema/schema>
-- Move the schema definition (typeDefs) to separate file in a new graphql folder and import this module/file in index.ts
-- Add a schma definition for a mutator that create a new book
- Read Resolvers <https://www.apollographql.com/docs/apollo-server/data/resolvers>
-- Move the resolvers to separate file in the graphql folder and import this module/file in index.ts
-- Move the books array to a separate file in a new data folder, and import this in the resolver module
-- Add a resolver to create a new book
- Read Generating TS types for your schema <https://www.apollographql.com/docs/apollo-server/workflow/generate-types>
-- Try to use this to make your resolvers type safe

## Exercise 4

### Lab 4.1 - Define a GraphQL schema

- Define a GraphQL schema for the api from the exercises in lecture 2. You can write this schema in any editor (you can install an extension to Visual Studio Code to get intellisence for GraphQL's SDL), but you can also use Apollo studio: <https://www.apollographql.com/docs/studio/getting-started/> they have a free plan you can us.

### Lab 4.2 - Create an Apollo GraphQL server

- Create an Apollo GraphQL server that implement the the schema from exercise 4.1 using the database from the exercises in lecture 2.
You may find some help here: <https://www.apollographql.com/docs/apollo-server/data/fetching-data>
