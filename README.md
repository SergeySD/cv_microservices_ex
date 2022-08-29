# Module 1 – Designing Microservices
## Exercise 1 – Lightweight IoT system

### Communication Model

I think that for bidirectional communication between IoT devices we can use a message broker based on the MQTT protocol. 

For telemetry, we can use protocol UDP to send telemetry messages directly to the telemetry microservice. Even if the microservice failed or is overloaded it will not cause massive faults in connected devices. 

I think that the most important part of the system is Registration. That will take the first strike in case of mass devices restart and it should be the most reliable service. It can use something simple maybe pure TCP or lightweight HTTP protocol. 

### Data stores

Because we have a wide range of devices with different data schema I suggest using schemaless databases like MongoDB, or Postgresql with JSON fields to store the device's state.

To store telemetry and registration events I suggest using column-based databases like ClickHouse

### Further optimizations

I think that all these 3 microservices should be scaled separately
because the Telemetry service load depends on the number of devices, Registration services load depends on how often it restarts, State service load depends on how often it changes the state

Maybe it makes sense to do geo separation of devices, devices from Europe will work with European servers, etc. It can be done on DNS using client IP.





