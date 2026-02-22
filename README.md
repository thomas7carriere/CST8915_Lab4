# CST8915_Lab4

Video Demo: https://youtu.be/6ebF4cBcqJg

- What are the main differences between a Docker image and a Docker container?
- A Docker image is the blueprint to create a Docker container. Using a DockerFile, a DockerImage is created in layers, with each layer corresponding to a line in the DockerFile. The resulting DockerImage then contains all the application code, runtime environments, libaries and so on, everything needed for the application to run. Docker then uses the DockerImage to create a DockerContainer as a instance of the app/service described by the DockerImage.
- Explain how Docker's layered architecture improves efficiency.
- By composing DockerImages of read-only layers, several containers of the same image can share all their common layers. This allows each container to only require a thin writable layer for updates, reducing the resource overhead of the containers.
- Why does each container get its own writable layer?
- A writeable layer is required as all other layers of the image are read-only, but the container still needs to be able to update itself. Rather than modifying existing layers, the writable layer can copy layers than need to be changed, and store a modified copy to be used by the container instance. If all containers shared a writable layer, any changes to one container would be shared across all containers of the same image.
- What are the benefits of using Docker Compose over running containers individually?
- Using Docker Compose we can create several containers at once with a single command. Additionally, Docker Compose creates all the containers on the same network, reducing the need for manual configurations for communication between containers. Only one command is required the stop the group(cluster?) of containers.
