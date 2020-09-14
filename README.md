# Goal

The application is a REST server that takes an integer as input and returns the prime numbers until it.
The app is currently distributed as a [docker container](https://github.com/orgs/travelaudience/packages/container/challenge-devops-rest-server/50705).

To test it:
```
docker run -p 9090:9090 ghcr.io/travelaudience/challenge-devops-rest-server:1.0.0
curl http://localhost:9090/primes?maxPrime=1000
```

## Task
The goal of this exercise is to take this application and make it work in a Kubernetes cluster.

We want to run the application in production, so you will need to provide/create all infrastructure configuration, app configuration, documentation, etc.

We expect it to be accessible from outside the cluster and we want it to be able to handle spikes in load.
The app exposes metrics in Prometheus format, this was done in anticipation of moving it to Kubernetes eventually.
Some kind of monitoring will be needed, so we know if the application is behaving properly.

Feel free to suggest processes and workflows around running this application in k8s. Assume this is the first application we migrate to Kubernetes and we want a proper setup. We will want to eventually migrate more apps to this k8s cluster.

## Return package
You must provide all instructions and code (or preferably a script) so we could spin up and test your environment easily.
Otherwise, we will not be able to properly evaluate the solution you created.

# Tips
- Feel free to setup any kind of CI/CD
- Feel free to use Minikube or any other tools to test your solution

## Details
* The server exposes a rest endpoint that allows to calculate all the primes till a certain provided number
* The server exposes a endpoint with prometheus metrics in order to allow integration with a monitoring tool
