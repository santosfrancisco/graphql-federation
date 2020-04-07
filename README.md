# Graphql apollo federation

Apollo server created using [Apollo federation](https://www.apollographql.com/docs/apollo-server/federation/introduction/)

I'm following [this article](https://medium.com/become-developer/is-it-possible-to-use-graphql-as-an-api-gateway-c9462efd5449) from Tom Saito

## How to run

Run `yarn install` the start script in the `book-service`

```bash
  cd book-service
  yarn install
  yarn start
```

Open [http://localhost:9002](http://localhost:9002) and run this query

```graphql
  query{
    stock{
      bookId
      price
      inStock
    }
  }
```

Run `yarn install` the start script in the `stock-service`

```bash
  cd stock-service
  yarn install
  yarn start
```

Open [http://localhost:9001](http://localhost:9001) and run this query

```graphql
  query{
    library{
      id
      title
      author
    }
  }
```

And run `yarn install` and start script in the root for run the gateway

```bash
  yarn install
  yarn start
```

Open [http://localhost:9000](http://localhost:9000) and run this query

```graphql
  query{
    library{
      id
      title
      author
      stock{
        bookId
        price
        inStock
      }
    }
  }
```