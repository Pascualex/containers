# Containers

## Setting up the environment

To set up the environment execute [set-environment.cmd](set-environment.cmd) or use the following commands.
  - Build the image using its [Dockerfile](./environment/Dockerfile):
    ```
    docker build -t containers-environment ./environment
    ```
  - Remove the previous image:
    ```
    docker image rm containers-environment
    ```

Currently the `containers-environment` image is equivalent to `maven:3.6.3-jdk-11`, but the current structure allows it to be customized if needed.

## Building the project

To build the project execute [build.cmd](build.cmd) or use the following commands.
  - Build the image using its [Dockerfile](./containers/Dockerfile):
    ```
    docker build -t containers ./containers
    ```
  - Remove the previous image:
    ```
    docker image rm containers
    ```

## Running the project

To run the project execute [run.cmd](run.cmd) or use the following command.
  - Using the projects image, run a container that will be removed once it finishes execution:
    ```
    docker run --rm containers
    ```
