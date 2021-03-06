# GitHub Actions Runner Docker images

![Docker Pulls](https://img.shields.io/docker/pulls/zerosuxx/github-actions-runner) ![GitHub Workflow Status](https://img.shields.io/github/workflow/status/zerosuxx/docker-github-actions-runner/Build%20Test%20and%20Push)

`zerosuxx/github-actions-runner:latest` is image that can be used to run GitHub Runner in container.

based on `ubuntu:18.04` image
pre installed apps:
 - `curl`
 - `git`
 - `docker`
 - `docker-compose`

## Usage with docker

`docker run -d --rm -e "RUNNER_REPOSITORY_URL=$RUNNER_REPOSITORY_URL" -e "RUNNER_TOKEN=$RUNNER_TOKEN" zerosuxx/github-actions-runner:latest`

## Usage with docker-compose

`RUNNER_REPOSITORY_URL=$RUNNER_REPOSITORY_URL RUNNER_TOKEN=$RUNNER_TOKEN docker-compose up -d`

## Environment variables

The following environment variables allows you to control the configuration parameters.

| Name | Description | Default value |
|------|---------------|-------------|
| `RUNNER_REPOSITORY_URL` | The runner will be linked to this repository URL | *Required* |
| `RUNNER_TOKEN` | Access Token provided by GitHub | *Required* |
| `RUNNER_WORK_DIRECTORY` | Runner's work directory | `"_work"` |
| `RUNNER_NAME` | Name of the runner displayed in the GitHub UI | `Hostname of the container` |

https://help.github.com/en/actions/automating-your-workflow-with-github-actions/adding-self-hosted-runners