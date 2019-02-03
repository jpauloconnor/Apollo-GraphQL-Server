# Terms

### Part 1
```Query type```: Entry point for schema. Describes the data to fetch.
```SDL```: GraphQL's SDL(Schema Definition Language)
```Scalar type```: a primitive type. 
```Object Type```: begins with `type`. Has properties and primitive types and object types.
```Mutation Type```: entry point into graph for modifying data. A special Object type.
```CustomType```: A good idea would be to add suffixes for the certain types, for instance a response type might have the following:

```graphql
type WaterSampleResponse {
    success: Boolean!
    message: String
    samples: [Sample]
}
```

```GraphQL Playground```: In browser IDE for writing queries.

```Introspection```: provides detailed info/documentation for the Graph's schema. 


### Part 2

### Part 3
```resolvers```: Provide instructions for turning a query, mutation or subscription into data. Return the specific type or a promise for the data. 

```graphql
fieldName: (parent, args, context, info) => data
```

```parent```: object that contains the result returned from the resolver on the parent type 
```args```: object that contains the arguments passed to the field
```context```: object shared bya ll resolvers. Conatins per-request state such as authentication
```info```: info about execution state used in advanced cases


```operation keyword```: Word used in a query in the playground to start. Use query or mutation.


```pagination```: ensures server only sends data in small chunnks. 

```cursor-based pagination```: uses a constant pointer(cursor) to keep track of order of data set. Eliminates skipping items and displaying the same item more than once.


### Part 4
```Apollo Engine```: has a schema registry that allows us to pull recent schema from the cloud

```Schema Explorer```: explore all types and fields in schema with usage stats. Cost of a field, which fields are in most demand

```Schema History```:  validate the new schema against field-level usage data from previous schema. Provide insights into which clients will be broken.

```Performance Analytics```: insights into every field, resolvers and operations

```Performance Alerts```: configure notifications to be sent to Slack. Alerts for threshold rate. 


```Publish schema to Apollo registry```:
```js
$ npx apollo service:push --endpoint=http://localhost:4000

```

2. Deploy graph API to the cloud
```js
$ npm now
```
3. It might want you to confirm your email first. You might have to run the above twice. You should receive a url like this: 
```js
https://server-8ocesaecc.now.sh
```

