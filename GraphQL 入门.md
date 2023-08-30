# GraphQL 入门

---

<img src="https://s2.loli.net/2022/05/18/KtBPdJmqQ3iGs6x.png" title="" alt="" width="803">

1. What is [GraphQL](https://graphql.org/)
   
   主要解决交流问题：‘ends’ （frontend、backend）communication，decouple communication process, introduce a rich new language
   
   Graph of objects with many relations between them. (REST：resources in URLs - Uniform Resource Locator)
   
   1. big picture
      
      ![](https://s2.loli.net/2022/05/19/DKIkHxZcTAtEOfg.png)
      
      data APIs: SQL、GraphQL （[Dgraph](https://dgraph.io/)）
      
      ![](https://s2.loli.net/2022/05/19/JMG2qe3HY6jnitW.png)
      
      strong type system
   
   2. a [specification](https://spec.graphql.org/June2018/)
   
   3. a language: 与SQL对比较
      
      1. READ
      
      2. WRITE
      
      3. subscription （需要数据通道支持服务端推送，比如WebSocket）
   
   4. a service
      
      1. runtime layer
      
      2. structure - schema
      
      3. behavior - resolver function
      
      4. query
         ![](https://s2.loli.net/2022/05/26/tjHW4TFDlcyqhp6.png)
      
      5. schema
         ![](https://s2.loli.net/2022/05/26/PBl6YkV2AQ4SuE5.png)
      
      6. response
         
         ```jsonp
         {
         "id": 42,
         "first_name": "Jane",
         "last_name": "Doe",
         "email":"jane@doe.name",
         "birth_date": "01/01/1990",
         "hire_date": "01/01/2020"
         }
         ```
         
         ```javascript
         // Resolver functions 
         const name => (source) => `${source.first_name} ${source.last_name}`; 
         const email => (source) => source.email;
         ```
         
         ```graphql
         {
             data: 
             { 
                 employee: 
                 { 
                     name: 'Jane Doe', 
                     email: 'jane@doe.name' 
                 } 
             }
         }
         ```

2. Why GraphQL
   
   ![](https://s2.loli.net/2022/05/26/6dB4UhDO3tMEIJi.png)
   
   ![](https://s2.loli.net/2022/05/26/P6IhHmWvYo9rfVg.png)
   
   ![](https://s2.loli.net/2022/05/26/6AQlrgRfk9xbhNU.png)
   
   1. REST APIs?
      
      1. GET\POST\PUT\DELETE\PATCH
      
      2. GET /users; GET /users/23; PUT /users; PUT /users/23; Delete /users/23; GET /users/23/comments
      
      3. ![](https://s2.loli.net/2022/06/09/rRM7fuO3tVIxaB2.png)
   
   2. The GraphQL way
      
      1. The typed graph schema
      
      2. The declarative language
      
      3. The single endpoint and client language
      
      4. The simple versioning
   
   3. in action

3. Problems
   
   1. Security
   
   2. Caching and optimizing
   
   3. Learning curve
