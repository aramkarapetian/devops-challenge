# Solution instructions

## Requirements
1. Solution requires kubernetes cluster in place with version that supports custom metrics
2. Current setup will expose service endpoint via load balancer (I have tested this against GCP/GKE)

## Current Setup
1. Configs are tuned with relatively optimal CPU and Memory limits for given application (adding more cpu would improve performance)
2. Configured for 400 request per second setup
3. Only one custom metric from container is considered
4. In values.yaml from rest-server max replicas and resources can be modified depending on requirements

## How to run
1. configure gcloud cluster and auth
2. `cd charts/infrastructure && make deploy`
3. `cd charts/rest-server && make deploy`
4. `ab -n 1000000 -c 500 http://$LOAD_BALANCER_PI/` should add load

## Improvements
1. would suggest standart naming across applications (even standard setup for different metrics). Then prometheus-adapter could be configured to automatically pick standart metrics
2. base chart for different types of applications which will standardize setup
3. standard grafana dashboards for each application type
4. standard CI setup configs (have not configured)