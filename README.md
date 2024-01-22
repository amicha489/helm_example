# Using Helm to manage k8s resources for several microservices in multiple environments

This example repo considers 3 'fictional' microservices (review, recommender, and favorites) living in 2 separate environments (prod & stage).

Under the example-chart/ folder, there are the 2 folders and a Chart.yaml.
- The files in the templates/ folder are for each k8s resource (ConfigMap, Deployment, Service, ServiceAccount, ...)
- In the values/ folder, there is a base.yaml values file for 'shared' values between microservices, and prod/ and stage/ folders for microservice specific values files (i.e. prod/review.yaml has values for the Review microservice in prod, stage/favorites.yaml has values for the Favorites microservice in stage, ...).

Finally, there is a Taskfile to run helm templating commands for convenience. There are commands to template for each of the 3 microservices in each of the 2 environments (so 6 tasks).

The purpose of this example is to show that this architecture and structure allows for expandability and scalability: we can easily add another environment and/or we can easily add another microservice as we please.
