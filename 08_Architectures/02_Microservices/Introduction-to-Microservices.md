# What is a microservice? What is a microservice-based architecture?

Starting in 2009 — driven completely by APIs and riding the initial wave of what we would come to know as microservices — Netflix completely redefined its application development and operations models. At the time, the rest of the technology landscape was littered with Enterprise-scale monoliths, however, Netflix doubled down their effort to build more manageable, more scalable, and more resilient distributed systems.

The Netflix definition of microservices is “fine-grained SOA (service-oriented architecture)”. You don’t need to be intimately familiar with SOA (an architecture style coined more than a decade ago), just the terms used in the acronym. Ideally, you are building an entire architecture out of services from day one. In microservices, each of these services has a single solitary purpose with no side effects, enabling you to cover greater scale with fewer overall dedicated engineers.

## But what is a microservice? What is a microservice-based architecture?

In essence, microservices and microservices-based architectures are many smaller architectural components, built and delivered faster, becoming stronger, both independently and as a whole.

## Microservices are smaller

Microservices means no more monoliths. Monoliths are often big, clunky, slow, and inefficient. We are moving away from a world with 2GB WAR files (yes, just the WAR file—not the application server or operating system components) to a world populated by many services of 500MB each, containing entire applications, servers, and necessary operating system components.

The migration from mainframes to client/server architectures was a large step and one that many companies and developers alike struggled with. The more recent migration from core web-based application servers to SOA adoption was a similar struggle. Many components included in application servers of years past lend themselves to microservices; however, they are still packed inside multi-gigabyte installation binaries. The next figure, for example, shows the architecture of a traditional web application architecture, deployed using WebSphere Application Server and Java Enterprise Edition components.

Microservices are an exercise in integration with all interacting components being much more loosely coupled. The entire idea of microservices becomes plug and play. I will touch on this more in the Stronger section, but essentially a microservices-based system employs the shotgun method at scale, to maintain and secure more small components instead of fewer large components. You remove single points of failure and distribute those points of failure everywhere.

Building for failure can only be done with smaller pieces. If you build a monolith for failure, you spend too much time focusing on the inefficiencies of every edge case. If you build a single service instance for failure, other service instances take over when consumers make requests.

