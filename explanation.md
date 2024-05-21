# Explanation

## Order of Execution

1. **common**: Updates and upgrades apt packages to ensure the server is up to date.
2. **docker**: Installs Docker and starts the Docker service to facilitate container management.
3. **frontend**: Builds the frontend Docker image and runs the container to host the frontend of the E-commerce application.
4. **backend**: Builds the backend Docker image and runs the container to host the backend of the E-commerce application.
5. **mongodb**: Runs the MongoDB container to provide data storage for the application.

## Ansible Modules

- `apt`: Used for managing apt packages to ensure the server is properly configured.
- `git`: Clones the GitHub repository containing the E-commerce application code.
- `command`: Executes shell commands to perform various setup tasks.
- `docker_container`: Manages Docker containers for hosting the application components.
- `uri`: Verifies application endpoints to ensure the application is running correctly.

## Project Structure

The project follows a structured layout for organization and modularity:

- **Vagrantfile**: Defines the virtual machine configuration for Vagrant provisioning.
- **playbook.yml**: Main Ansible playbook orchestrating the setup tasks for the application.
- **vars/main.yml**: Variable file containing container names used in the playbook.
- **roles/**: Directory containing Ansible roles for different components of the application.
  - **common/**: Role for updating apt packages.
  - **docker/**: Role for installing and managing Docker.
  - **frontend/**: Role for setting up the frontend Docker container.
  - **backend/**: Role for setting up the backend Docker container.
  - **mongodb/**: Role for running the MongoDB container.

