## Remove all containers

- Let's remove stacks, services, and containers before we continue

.exercise[

  ```bash
  docker stack rm $(docker stack ls)
  sleep 5
  docker service rm $(docker service ls -q)
  sleep 5
  docker rm -f $(docker ps -q)
  ```

]

- Let's remove Swarm

.exercise[

  ```bash
  docker node demote node2 node3
  docker node rm node2 node3 -f
  ssh node2 docker swarm leave -f 
  ssh node3 docker swarm leave -f
  docker swarm leave -f
  ```

]
