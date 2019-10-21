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

---

## Shutdown Swarm

- Let's disable Swarm in Docker (but leave Docker running for Kubernetes)
- For node2/3 we need to:
  - demote to worker
  - remove it from node list on node1 (only manager left)
  - ssh into 2/3 and tell them to leave
- Lastly, force node1 to leave the Swarm

.exercise[

  ```bash
  docker node demote node2 node3
  docker node rm node2 node3 -f
  ssh node2 docker swarm leave -f 
  ssh node3 docker swarm leave -f
  docker swarm leave -f
  ```

]
