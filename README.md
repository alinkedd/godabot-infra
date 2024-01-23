# godabot-infra

Infrastructure for the [`godabot`](https://github.com/alinkedd/godabot) app.

## Course tasks

### Prompts for `yaml` files

|NAME|PROMPT|DESCRIPTION|EXAMPLE|
|----|------|-----------|-------|
|app.yaml|generate basic app.yaml file for pod to have europe-central2-docker.pkg.dev/godabot/godabot-dev-gcr/godabot:v0.0.5-bfcec15-linux-amd64 container with labels and names being godabot or related to godabot and with reference to regcred to pull image|main app pod|[example](./yaml/app.yaml)|
|app-livenessProbe.yaml|generate basic pod yml with nginx container and liveness probe with recommended parameters at default port|nginx server with livenessProbe|[example](./yaml/app-livenessProbe.yaml)|
|app-readinessProbe.yaml|generate basic pod yml with nginx container and liveness and readiness  probe with recommended parameters at default port|nginx server with liveness and readiness probes|[example](./yaml/app-readinessProbe.yaml)|
|app-volumeMounts.yaml|generate basic pod yml with nginx container with host volume containing static assets mounted to default serving directory|nginx server with serving directory having access to external volume|[example](./yaml/app-volumeMounts.yaml)|
|app-cronjob.yaml|generate basic cronjob yml to run hello-world every 2 minutes|hello world every 2 minutes|[example](./yaml/app-cronjob.yaml)|
|app-job.yaml|generate basic job file example to migrate sqllite database per your understanding|example: job to migrate db|[example](./yaml/app-job.yaml)|
|app-multicontainer.yaml|generate basic multicontainer pod yml to have nginx and httpd containers within shared directory where every of the servers mounts to its default serving directory|two servers with distinct working directory|[example](./yaml/app-multicontainer.yaml)|
|app-resources.yaml|generate basic pod yml with nginx container and resources limits and requests  with recommended values for small test server|nginx with defined limits and requests|[example](./yaml/app-resources.yaml)|
|app-secret-env.yaml|generate basic pod yml containing sqlite db with some default credentials in env from dbsecret|db pod with credentials|[example](./yaml/app-secret-env.yaml)|
