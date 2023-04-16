# Simple Auto Scaler for A Simple Web Service

- This small project is to create a auto scaler that actively monitors the arrival rate, response time,
and number of replications of a simple web service, and scale up / down the number of relications of 
this web service based on demand. The scaling policy is based off The Queuing Theory and The Queuing 
Rule of Thumb.
- This simple web service was written `Flask`, and only have one route (`\`). Each time a request was 
received, this service will simply sleep for a random amount of time to pretend that it's doing some 
difficuly computation. Then, it will return a response that contains number of visitors that have 
visited this web service and the amount of sleep time. 
- This simple web service is original deployed in two VM clusters provided by Cybera Rapid Access Cloud,
and runs in Docker swarm mode.
- An real time visualizer is implemented to visualize the workload, response time,and number of replications.
