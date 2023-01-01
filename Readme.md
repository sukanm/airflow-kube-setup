# Airflow Kubernetes Setup

> This setup is used and tested in airflow 1.10.10. It's a good idea to use latest version of Airflow 2.3.x+. Need help setting up infrastructure and training your team? Contact me bhavanicodes@gmail.com 

The setup files are copied directly from airflow's repo and modified to fit the requirements.

One major change is instead of building the docker image from source, we use `pip` to install airflow

## Create Docker Image

```
cd scripts/docker
docker build -t airflow .
```

> Push the image to your favorite registry and get the URL

## Deploy in kubernetes

1. Find $IMAGE in the repository
2. Find $TAG in the repository
2. Change it with the docker image URL and tag respectively

```
cd scripts/
./kube/deploy.sh -d persistent_mode
```
The other supported modes is `git_mode`

## Walkthrough blog

[Deploying airflow on kubernetes](https://bhavaniravi.com/blog/deploying-airflow-on-kubernetes/)
