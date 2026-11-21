# Complete the Dockerfile Code

## Aim
To complete TODO 1, TODO 2 and TODO 3 in the given Dockerfile and run the result portal using Docker.

## Completed TODOs

**TODO 1:** Set the working directory to /app.

**TODO 2:** Copy the application source files and create a non-root user named portal.

**TODO 3:** Expose port 8000 and start the application using Gunicorn on 0.0.0.0:8000.

## Execution Commands

```bash
docker build -t result-portal .
docker run -d --name result-portal -p 8000:8000 result-portal
docker ps
docker exec result-portal whoami
```

## Expected Output

The Docker image builds successfully, the container runs, and the application is accessible at http://localhost:8000.

The container user should be portal.

## Result

All three TODO sections are completed in the Dockerfile, and the result portal is configured to run inside a Docker container.
