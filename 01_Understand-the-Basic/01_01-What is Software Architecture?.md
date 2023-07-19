# What is Software Architecture?


Software Architecture
Describes how an application is built
including its components, how they
interact with eachother, environment
in which they operate and so on.

Software architecture is concerned with context, which can be split into three main areas:

#### The functional requirements:
    – What should a particular system do?
#### Non-functional requirements (the ‘ilities’):
    – Functionality
    – Reliability
    – Usability
    – Efficiency
    – Maintainability
    – Scalability
#### Restrictions
    – Legal requirements
    – Standards
    – Cost
    – Time-to-market
    – Talent hiring


## Common software architecture structures

### 1. Layered pattern architecture

This database-driven architecture is probably the most common approach as it is a great way to store information effectively in tables. It has been used for some of the biggest software frameworks like Express, Java EE, and Drupal. In a layered approach, the data begins at the top layer and works its way down until it reaches the bottom (which is typically a database). As it descends, each layer has a different task which focuses the data and solves issues such as reformatting the values.

### 2. Event-driven architecture

This approach is agile and with high performance. Large numbers of programs spend the majority of their time waiting for an event to occur (such as a human using a computer). It is built around the idea that sometimes data will need to be processed, and other times it won’t. This is managed through a central unit that processes all the data sent to it, before delegating them to the relevant modules.

Where a layered architecture will pass data through all levels, event-driven architectures will only send the data to the appropriate location; hence, why they are considered highly efficient. This architecture is great at adapting to complex environments. It can be scaled easily and extended if new event types are used. However, testing can only be done on individual modules if they are independent, otherwise, they will have to be tested in a fully functional system. Error handling can be challenging to structure if several modules are handling the same events.

### 3. Monolithic Architecture
This kind of architecture is called a monolith because there's a single server application that is responsible for all the features of the system.The main benefit of a monolithic design is its simplicity. The functioning of it and the set up required is simple and easy to follow, and this is why most applications start out in this way.

### 4. Microservices Architecture
We could define it as the concept of dividing server side features into many small servers that are responsible for only one or a few specific features.

All this communication happens through APIs just like with a regular monolithic server (or through other communication systems like Kafka or RabbitMQ). The only difference is that now we have different servers responsible for different actions instead of a single one that does it all.

This sounds a bit more complex, and it is, but microservices offer us the following benefits:

* You can scale particular services as needed, instead of scaling the whole back end at once. Following our example, when we started to experience performance issues we vertically scaled our whole server – but actually the feature that requested the more resources was only the streaming. 
* Features will be more loosely coupled, which means we'll be able to develop and deploy them independently.
* The codebase for each server will be much smaller and simpler. Which is nice for the dev folks that have been working with us from the start, and also easier and quicker for new developers to understand.

Microservices is an architecture that is more complex to set up and manage, which is why it makes sense only for very big projects. Most projects will start out as monoliths and migrate to microservices only when needed for performance reasons.

### 5. Back-end for front-end (BFF)

One problem that comes up when implementing microservices is that the communication with front-end apps gets more complex. Now we have many servers responsible for different things, which means front-end apps would need to keep track of that info to know who to make requests to.

Normally this problem gets solved by implementing an intermediary layer between the front-end apps and the microservices. This layer will receive all the front-end requests, redirect them to the corresponding microservice, receive the microservice response, and then redirect the response to the corresponding front-end app.

The benefit of the BFF pattern is that we get the benefits of the microservices architecture, without over complicating the communication with front-end apps.

### 6. Load balancers and horizontal scaling

 Load balancers act as reverse proxys to our servers, intercepting client requests before they get to the server and redirecting that request to the corresponding server.

You should know that horizontal scaling is also possible with databases as it's possible with servers. One way of implementing this is with a source-replica model, in which one particular source DB will receive all write queries and replicate it's data along one or more replica DBs. Replica DBs will receive and respond to all read queries.

The advantages of DB replication are:

* Better performance: This model improves performance allows more queries to be processed in parallel.
* Reliability and availability: If one of your database servers is destroyed or inaccessible for any reason, data is still preserved in other DBs.

## Where Your Infrastructure Lives
There're mainly three options when deciding where and how to host an application: on premise, on traditional server providers, or on the cloud.

### On-Premise Hosting
On premise means you own the hardware in which your app is running. In the past this used to be the most traditional way of hosting applications. Companies used to have dedicated rooms for servers to be in and teams dedicated to the set up and maintenance of the hardware.

One situation in which on premise servers still make sense is when dealing with very delicate or private information. Think about the software that runs a power plant, or private banking information, for example. Many of these organizations decide to have on premise servers as a way to have complete control over their software and hardware.

### Traditional Server Providers
A more comfortable option for most companies are traditional server providers. These are companies that have servers of their own and they just rent them. You decide what kind of hardware you'll need for your project and pay a monthly fee for it (or some amount based on other conditions).

What's great about this option is that you don't need to worry about anything hardware-related anymore. The provider takes care of it, and as a software company you only worry about your main goal, the software.

Another cool thing is that scaling up or down is easy and risk free. If you need more hardware, you pay for it. And if you don't need it anymore, you just stop paying.


### Hosting on the Cloud
If you've been around technology for a little while you've probably heard the word "cloud" more than once. At first it sounds as something abstract and kind of magical, but actually what's behind it is nothing more than huge data centers owned by companies like Amazon, Google, and Microsoft.

Using different services like AWS (Amazon web services), Google Cloud, or Microsoft Azure, we're able to host our applications in these companies' data centers and take advantage of all that computing power.

When getting to know cloud services, it's important to notice that there are many different ways in which you can use them:

#### Traditional
The first way is to use them in a similar way you'd use a traditional server provider. You select the kind of hardware you want and pay exactly for that on a monthly basis.

#### Elastic
The second way is to take advantage of the "elastic" computing offered by most providers. "Elastic" means that the hardware capacity of your application will automatically grow or shrink depending on the usage your app has.

For example, you could start out with a server that has 8gb of RAM and 500gb of disk space. If your server starts getting more and more request and these capacities are no longer enough to provide good performance, the system can automatically perform vertical or horizontal scaling.

The awesome thing about this is you can configure all this beforehand and not have to worry about it again. As the servers scale up and down automatically, you pay only for the resources you consume.

#### Serverless
Another way in which you can use cloud computing is with a serverless architecture.

Following this pattern, you wont have a server that receives all requests and responds to them. Instead you'll have individual functions mapped to an access point (similar to an API endpoint).

These functions will execute each time they receive a request and perform whatever action you programmed them for (connecting to a database, performing CRUD operations or whatever else a you could do in a regular server).

What's very nice about serverless architecture is that you forget all about server maintenance and scaling. You just have functions that get executed when you need them, and each function is scaled up and down automatically as needed.

As a costumer, you pay only for the amount of times the function gets executed and the amount of processing time each execution lasts.



## Common Concepts

### Client-server Model
Client-server is a model that structures the tasks or workloads of an application between a resource or service provider (server) and a service or resource requester (client). 

### APIs
API (application programming interface) is nothing more than a set of defined rules that establishes how an application can communicate with another. Having this set of rules, the client knows exactly what it has to require in order to complete a certain task, and the server knows exactly what the client will require when a certain action has to be performed.

### Modularity
The practice of dividing big things into smaller pieces. This practice of breaking things down is performed to simplify big applications or codebases.

Modularity has the following advantages:

* It's good for dividing concerns and features, which helps with the visualization, understanding, and organization of a project.
* The project tends to be easier to maintain and less prone to errors and bugs when it's clearly organized and subdivided.
* If your project is subdivided into many different pieces, each can be worked on and modified separately and independently, which is often very useful.

## Sources

An Introduction to Software Architecture Patterns: https://www.freecodecamp.org/news/an-introduction-to-software-architecture-patterns/

Software Architecture: It might not be what you think it is: https://www.infoq.com/articles/what-software-architecture/