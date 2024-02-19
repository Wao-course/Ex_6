# Lecture 06 Excercises

## Exercise 1 - Hello world

### Lab 1.1

- Download/use the demo graphql-demo from the demos folder.
- Run npm i
- Run the app with npm start and acces the graphQL endpoint in your browser.
Try to access the the graphQL endpoint from Postman.

### Lab 1.2

The demo app uses old versions of dependencies. Your task is to update it to use the newest versions - how do you do this smart?
> we need to run ```bash 
npm update or yarn update```

### Lab 1.3

Change the demo app from JavaScript to Typescript. You can find help here <https://www.freecodecamp.org/news/how-to-use-typescript-with-graphql/>
> installing typescript and express-graphql and updating the package.json to use ts-node instead of node  
```bash
npm install graphql express express-graphql
npm install -D nodemon ts-node @types/express typescript
```



## Exercise 2 - Using GraphiQL to explore an API

### Lab 2.1

Navigate to <https://docs.github.com/en/graphql/overview/explorer> and explore what kind of information you can get from GitHub.

1. Try an Introspective query.
    You can get help here: <https://graphql.org/learn/introspection/>

    > The introspection query is a GraphQL query that returns information about the schema of a GraphQL API. It is a useful tool for understanding the types and structure of an API. The introspection query is a standard part of the GraphQL specification and is supported by most GraphQL services.

    ```graphql
    query IntrospectionQuery {
    __schema {
        types {
        name
        description
        fields {
            name
            description
                }  
            }
        }
    }
        ```


2. Use intellisense in GraphiQL to build some queries.


### Lab 2.2

Another site you may explore is the Star Wars service at <https://graphql.org/swapi-graphql>

1. Write a query that will list all films, and for each film show title and the name of all species that appear in the movie.
    > The query is as follows:
    ```graphql
    query {
    allFilms {
        films {
        title
        species {
            name
             }
            }
        }
    }
    ```

2. Use intellisense in GraphiQL to build some queries - you decide what you want to know. 

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


## Exercise 4 - Define a GraphQL schema

### Lab 3.1

Define a GraphQL schema for a hotel booking system. Using this schema, it should be possible to query for available rooms and specify some properties for the required room.
And it should also be possible to book a room.
You can write this schema in any editor (you can install an extension to Visual Studio Code to get intellisence for GraphQL's SDL), but you can also use Apollo studio: <https://www.apollographql.com/docs/studio/getting-started/> they have a free plan you can us.

> The schema is as follows:
```graphql
type Order {
  id: ID!
  material: String!
  amount: Int!
  currency: String!
  price: Float!
  timestamp: String!
  delivery: Delivery!
}

type Delivery {
  first_name: String!
  last_name: String!
  address: Address!
}

type Address {
  street_name: String!
  street_number: String!
  city: String!
}

type Query {
  orders: [Order!]!
  order(id: ID!): Order
}

type Mutation {
  createOrder(input: OrderInput!): Order!
  updateOrder(id: ID!, input: OrderInput!): Order!
  deleteOrder(id: ID!): Order!
}

input OrderInput {
  material: String!
  amount: Int!
  currency: String!
  price: Float!
  timestamp: String!
  delivery: DeliveryInput!
}

input DeliveryInput {
  first_name: String!
  last_name: String!
  address: AddressInput!
}

input AddressInput {
  street_name: String!
  street_number: String!
  city: String!
}

```
- We define a Order type representing an order with fields id, material, amount, currency, price, timestamp, and delivery.
- The Delivery type represents the delivery information with fields first_name, last_name, and address.
- The Address type represents the address with fields street_name, street_number, and city.
- We define queries to fetch orders (orders) and a single order by its ID (order).
- We define mutations to create (createOrder), update (updateOrder), and delete (deleteOrder) orders.
- Input types OrderInput, DeliveryInput, and AddressInput are defined for creating and updating orders, which are used as arguments in mutations.


### Lab 4.2 - Create an Apollo GraphQL server

- Create an Apollo GraphQL server that implement the the schema from exercise 4.1 using the database from the exercises in lecture 2.
You may find some help here: <https://www.apollographql.com/docs/apollo-server/data/fetching-data>
