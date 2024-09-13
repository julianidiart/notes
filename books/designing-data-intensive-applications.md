# Designing Data Intensive Applications (2017)

## Part I. Foundations of Data Systems

### 1. Reliable, Scalable, and Maintainable Applications

- Summary

  - **Reliability**: Systems should continue to perform as expected, even in adverse conditions such as hardware failures or human errors.
    - A system is considered _reliable_ if it can perform its functions even when encountering faults. Hardware faults (like disk failures) are common but can be managed using redundancy. Software errors or human mistakes are more difficult to predict and often require thorough testing and monitoring to mitigate.
      > "Reliability means making systems work correctly, even when faults occur."
  - **Fault tolerance**: Design systems to tolerate hardware, software, or operational faults without service disruption.
    - Systems need to handle faults without degrading their overall service quality. Techniques like _redundancy_, _backups_, and _automated recovery processes_ ensure that the system can withstand hardware, software, and human errors.
      > "Fault-tolerance techniques can hide certain types of faults from the end user."
  - **Scalability**: Systems must handle increased load by effectively growing their capacity.
    - As systems grow, they face more demands. _Scaling_ can be achieved either by improving the capacity of a single machine (vertical scaling) or distributing the load across multiple machines (horizontal scaling). Different strategies, such as caching, load balancing, and partitioning, can help systems cope with growth.
      > "Scalability means having strategies for keeping performance good, even when load increases."
  - **Describing load**: Different metrics like requests per second or active users determine a system’s load; understanding this is key for scaling.
    - Accurately describing _system load_ (e.g., requests per second) and understanding its _performance_ under varying loads are essential for making scalability decisions. Performance bottlenecks can appear as load increases, requiring various optimizations and possibly architectural changes.
      > "Describing load and performance quantitatively is key to discussing scalability."
  - **Approaches for load handling**: Vertical scaling (adding more power to a machine) and horizontal scaling (adding more machines) can manage growing load, but each comes with challenges.
    > "Adding more machines (horizontal scaling) or enhancing individual hardware (vertical scaling) are common strategies to handle growing load."
  - **Maintainability**: Systems should be designed for long-term ease of modification and operational simplicity.
    - Good system design ensures ease of modification and _operational efficiency_. Systems should be structured to handle future changes gracefully, with minimal complexity to avoid technical debt. Clear _abstractions_ and _documentation_ help ensure the system is understandable and maintainable.
      > "Good operability means making routine tasks easy, allowing the operations team to focus their efforts on high-value activities."
  - **Operational concerns**: Engineers need the ability to monitor systems, quickly recover from faults, and anticipate issues before they occur.
    - Systems should provide clear _telemetry_ to allow engineers to monitor health, diagnose issues, and respond to failures effectively. Clear dashboards and alerts help preempt potential failures.
      > "Good operations can often work around the limitations of bad software, but good software cannot run reliably with bad operations."
  - **Simplicity**: Avoid unnecessary complexity, as it can slow down development and increase the chances of introducing errors.
    - Simple designs are easier to understand, modify, and debug. Avoiding unnecessary complexity reduces maintenance costs and the likelihood of introducing new bugs during changes.
      > "Reducing complexity greatly improves the maintainability of software, and thus simplicity should be a key goal for the systems we build."
  - **Evolvability**: Systems should easily adapt to changing requirements without needing massive rewrites.
    - The system should accommodate changing requirements over time, allowing engineers to add new features without massive rewrites. This requires careful design with flexible data models and modular code.
      > "It’s extremely unlikely that your system’s requirements will remain unchanged forever. They are much more likely to be in constant flux."
  - **Design Trade-offs**: Architects must make careful decisions balancing _reliability_, _scalability_, and _maintainability_ against _costs_ and _complexity_. Trade-offs like reducing reliability for better performance, or choosing simpler designs at the cost of more manual intervention, are inevitable.
  - **Future readiness**: As technologies evolve, a system’s ability to adapt is crucial for staying relevant. Design choices made today should support easy upgrades and minimize the effort required to adopt new technologies in the future.
    > "The ease with which you can modify a data system, and adapt it to changing requirements, is closely linked to its simplicity and its abstractions."
