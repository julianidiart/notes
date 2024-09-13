# System Design Interview (2020)

## Chapter 1: Scale From Zero to Millions of Users

- The chapter breaks down the journey of scaling a system into manageable steps, starting with a simple single-server setup. As traffic grows, the system must evolve by introducing load balancers, separating web and data tiers, implementing database replication, and introducing caches. Horizontal scaling becomes essential once vertical scaling reaches its limits. The chapter also covers the importance of content delivery networks (CDNs) and caching, database sharding, and state management. At each level of scale, redundancy, availability, and performance optimization are considered.

- **Single server setup**: Everything (web, cache, database) runs on a single server initially.

  > "A journey of a thousand miles begins with a single step, and building a complex system is no different."

  - A _single-server setup_ works for small-scale systems but lacks redundancy and scalability.

- **Traffic management**: Use load balancers to distribute traffic across multiple servers as the user base grows.

  > "A load balancer evenly distributes incoming traffic among web servers that are defined in a load-balanced set."

  - _Load balancers_ help distribute traffic across multiple servers, preventing any server from being overwhelmed.

- **Database scaling**: Separate databases from the web tier for better performance and scalability; introduce replication and sharding for scaling.

  - _Scaling_ the database involves separating the web and database tiers and choosing between SQL and NoSQL based on the application’s needs.

- **Vertical vs. horizontal scaling**: Vertical scaling has limits, horizontal scaling provides better redundancy.

  > "Vertical scaling has a hard limit. It is impossible to add unlimited CPU and memory to a single server."
  > "Horizontal scaling allows you to scale by adding more servers into your pool of resources."

  - _Vertical scaling_ adds power to a single server but has limits; _horizontal scaling_ distributes load across multiple servers for better performance.

- **Database replication**: Master-slave replication improves performance and reliability.

  > "In the master-slave model, all writes and updates happen in master nodes; whereas, read operations are distributed across slave nodes."

  - Database replication improves read performance and adds redundancy, allowing the system to handle failures.

- **Caching**: Implement a cache tier to store frequently accessed data and reduce the load on databases.

  > "A cache is a temporary storage area that stores the result of expensive responses or frequently accessed data in memory so that subsequent requests are served more quickly."

  - Adding caching at the server or application level reduces database load and improves response times.

- **CDN usage**: Use a CDN to deliver static content (images, videos) to users from locations closer to them, improving response times.

  - A CDN ensures static assets are served quickly by caching them at edge locations close to users.

- **Stateless web tier**: Moving state information (like user sessions) out of web servers into shared storage allows for easier scaling and better fault tolerance.

  > "Stateless architecture: HTTP requests from users can be sent to any web servers, which fetch state data from a shared data store."

  - Moving to a stateless web tier allows easier scaling by adding or removing web servers based on demand.

- **Sharding**: Split large datasets across multiple databases, allowing for greater scalability while handling huge amounts of data.

- **Failure management**: Introduce failover mechanisms to deal with server or database crashes, maintaining availability.

- **Decoupling system components**: Use message queues to decouple system components and enable independent scaling of different services.

- **Global scaling**: Support multiple data centers across different regions to ensure low latency for a global user base.

  - Supporting multiple data centers also provides disaster recovery and improves performance for users in different geographical locations.

- **Message queues**: Asynchronous message processing decouples components and improves scalability.

  > "A message queue is a durable component, stored in memory, that supports asynchronous communication."

  - Using a message queue decouples tasks like image processing, allowing the system to handle asynchronous processing without delaying user responses.
