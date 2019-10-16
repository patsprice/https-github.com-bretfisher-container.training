name: cicd

# CI/CD for Docker and orchestration

A quick note about continuous integration and deployment

- This lab won't have you building out CI/CD pipelines

- We're cheating a bit by using only pre-built images on server hosts and not in CI tool

- Docker and orchestration works with all the CI and deployment tools

---

## CI/CD general process 

- Have your CI build your images, run tests *in them* (docker-compose is good for this)

- If you security scan, do it then on your images after tests

- After success, it pushes to registry. These "build artifacts" are ready for deployment

- Optionally, have CI do continuous deployment if build/test/push is successful

- CD tool would SSH into nodes and use docker/swarm/kubernetes CLI, or use remotely

- If supported, it could use docker/swarm/kubernetes API remotely

- Docker KBase [Development Pipeline Best Practices](https://success.docker.com/article/dev-pipeline)

- Docker KBase [Continuous Integration with Docker Hub](https://success.docker.com/article/continuous-integration-with-docker-hub)

- Docker KBase [Building a Docker Secure Supply Chain](https://success.docker.com/article/secure-supply-chain)

---

class: pic

![CI-CD with Docker](images/ci-cd-with-docker.png)
