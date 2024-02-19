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


## Exercise 3 - Define a GraphQL schema

### Lab 3.1

Define a GraphQL schema for a hotel booking system. Using this schema, it should be possible to query for available rooms and specify some properties for the required room.
And it should also be possible to book a room.
You can write this schema in any editor (you can install an extension to Visual Studio Code to get intellisence for GraphQL's SDL), but you can also use Apollo studio: <https://www.apollographql.com/docs/studio/getting-started/> they have a free plan you can us.

> The schema is as follows:
```graphql
# Define the Room type
type Room {
  id: ID!
  number: String!
  type: String!
  capacity: Int!
  price: Float!
  booked: Boolean!
}

# Define the Booking type
type Booking {
  id: ID!
  roomId: ID!
  guestName: String!
  startDate: String!
  endDate: String!
}

# Define the Query type
type Query {
  # Query to retrieve all available rooms
  availableRooms: [Room!]!
}

# Define the Mutation type
type Mutation {
  # Mutation to book a room
  bookRoom(roomId: ID!, guestName: String!, startDate: String!, endDate: String!): Booking!
}
```
- We have a Room type representing a hotel room, with fields such as id, number, type, capacity, price, and booked.
- We have a Booking type representing a booking made by a guest, with fields such as id, roomId, guestName, startDate, and endDate.
- We have a Query type with a single field availableRooms, which returns a list of available rooms.
- We have a Mutation type with a single field bookRoom, which allows booking a room by providing the roomId, guestName, startDate, and endDate.