# Bare bone auto scaler for web services

- This repository contains the bare-boned implementation of an auto scaler for web services that runs in Docker.
- It can actively monitors the arrival rate, response time and number of replications of a web service, and scale up / down the number of relications of a web service based on demand.
- The scaling policy is based off The Queuing Theory and The Queuing Rule of Thumb.

## Testing

### Example web service

- There's a simple web service included for testing purpose.
- It was written `Flask`, and only have one route (`\`).
- Each time a request was received, this service will
  1. sleep for a random amount of time to pretend that it's doing some difficuly computation,
  2. return a response that contains number of visitors that have visited this web service and the amount of sleep time.

### Test Environment

- The bare minimal testing requirement for this is to have at least two different hosts that have Docker install.
- One of the host (swarm manager node) will need to enable Docker swarm mode with `docker swarm init`.
- The remaining hosts (worker nodes) will need to join the swarm manager node with `docker swarm join`.

### Visualizer

- An real time visualizer is implemented to visualize the workload, response time,and number of replications.
