## Remove all containers

- Lets remove stacks, services, and containers before we continue

.exercise[

  ```bash
  docker stack rm $(docker stack ls)
  sleep 5
  docker service rm $(docker service ls -q)
  sleep 5
  docker rm -f $(docker ps -q)
  ```

]
