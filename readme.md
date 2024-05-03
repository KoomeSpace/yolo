# Dockerized React-Node Application

This project demonstrates how to Dockerize a React-Node application using Docker containers. It includes separate Dockerfiles for the frontend (React) and backend (Node.js) applications, as well as a Docker Compose file to orchestrate the deployment of multiple services.

## Requirements

Make sure you have Docker installed on your system.


## Dockerfiles

### Frontend Dockerfile (`Dockerfile.frontend`)

The frontend Dockerfile is responsible for building the React app.

1. **Stage 1: Build React app**
   - **Base Image**: `node:13-alpine`
   - **Working Directory**: `/app`
   - **Copy Package Files**: Copy `package.json` and `package-lock.json` to the working directory.
   - **Install Dependencies**: Run `npm install` to install dependencies based on the package files.
   - **Copy Source Code**: Copy the entire frontend directory.
   - **Build**: Run `npm run build` to build the React app.

2. **Stage 2: Use lightweight HTTP server to serve built files**
   - **Base Image**: `node:13-alpine`
   - **Working Directory**: `/app`
   - **Copy Built Files**: Copy the built files from the previous stage (`/app/build`) to the working directory.
   - **Expose Port**: Expose port `3000`.
   - **Command**: Start a lightweight HTTP server to serve the built files.

### Backend Dockerfile (`Dockerfile.backend`)

The backend Dockerfile is responsible for building the Node.js app.

1. **Stage 1: Build Node.js app**
   - **Base Image**: `node:13-alpine`
   - **Working Directory**: `/app`
   - **Copy Package Files**: Copy `package.json` and `package-lock.json` to the working directory.
   - **Install Dependencies**: Run `npm install` to install dependencies based on the package files.
   - **Copy Source Code**: Copy the entire backend directory.
   - **Build Script**: Add any build scripts here if necessary (not included in the provided template).

2. **Stage 2: Use Node.js to serve built files**
   - **Base Image**: `node:13-alpine`
   - **Working Directory**: `/app`
   - **Copy Built Files**: Copy the built files from the previous stage (`/app`) to the working directory.
   - **Expose Port**: Expose port `3001`.
   - **Command**: Start the Node.js server (command may vary based on your backend setup).

These Dockerfiles follow a multi-stage build approach to optimize the final image size. They use the `node:13-alpine` base image, which is a lightweight version of Node.js, and leverage Docker's layer caching mechanism to minimize build times.

