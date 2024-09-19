# Run UR5e Robot on ROS2 Humble Using Docker
This README provides a streamlined setup process for running a UR5e robot (the ones available in our lab) using ROS2 Humble and Docker.

## Prerequisites
Before you begin, ensure you have the following installed:
- Docker
- Docker Compose

## Setup Instructions
1. Create a Directory to store this repository
1. Clone the Repository
    ```
    git clone <repository-url>
    cd <repository-directory>
    ```
1. Build the Docker Containers 
    \
    When running for the first time, build the necessary Docker containers. From the cloned repository directory, execute:
    ```
    docker compose build
    ```
    This process may take approximately 20 minutes.

1. Run the System
    Note: If you encounter the following error message:
    ```
    Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: exec: "/entrypoint.sh": permission denied: unknown
    ```
    Resolve this by making the entrypoint scripts executable. Navigate to the directory containing the entrypoint files and run:
    ```
    chmod +x entrypoint.sh devel_entrypoint.sh
    ```
    After adjusting the permissions, repeat Steps 3 and 4. The startup process should complete more quickly this time.


