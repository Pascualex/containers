# Containers

The purpose of this project is to provide a basic structure for a container-based project, where two images are used:
 - `containers-environment` provides everything needed to compile the project.
 - `containers` is the result of compiling the project.

This way the only program required, to both compile and run the project, is Docker.

## Setting up the environment

To set up the environment, execute [set-environment.cmd](set-environment.cmd) or use the following commands.
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

To build the project, execute [build.cmd](build.cmd) or use the following commands.
  - Build the image using its [Dockerfile](./project/Dockerfile):
    ```
    docker build -t containers ./project
    ```
  - Remove the previous image:
    ```
    docker image rm containers
    ```

## Running the project

To run the project, execute [run.cmd](run.cmd) or use the following command.
  - Using the projects image, run a container that will be removed once it finishes execution:
    ```
    docker run --rm containers
    ```
