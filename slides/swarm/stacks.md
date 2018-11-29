class: btp-manual

# Swarm Stacks

- Compose is great for local development

- The Docker team designed the Compose file format to work in Swarm too!

- Compose files *v2* are great for local development

- Compose files *v3* can also be used for Swarm (and Kubernetes) deployments!

- "Compose files" and "Stack files" are really the same thing

---

## Compose file version 3

(New in Docker Engine 1.13)

- Almost identical to version 2

- Can be directly used by a Swarm/K8s cluster through `docker stack ...` commands

- Introduces a `deploy` section to pass orchestator-specific parameters

- Resource limits are moved to this `deploy` section

---

## Our first stack

- All the stack files that we will use are in the `stacks` directory

.exercise[

- Go to the `stacks` directory:
  ```bash
  cd ~/container.training/stacks
  ```

- Check `dockercoins.yml`:
  ```bash
  cat dockercoins.yml
  ```

]

---

## Deploying our first stack

- All stack manipulation commands start with `docker stack`

- Under the hood, they mostly map to `docker service` commands

- They also create networks, volumes, secrets, and configs

- Stacks have a *name* (which also serves as a namespace)

.exercise[

- Deploy our stack of apps:
  ```bash
  docker stack deploy --compose-file dockercoins.yml dockercoins
  ```

]

We can now connect to any of our nodes on port 8000, and see the hashing speed graph.

---

## Inspecting stacks

- `docker stack` has several informational sub-commands:

.exercise[

- Show all our stacks:
  ```bash
  docker stack ls
  ```

- Show all our services in the stack:
  ```bash
  docker stack services dockercoins
  ```

- Show all our containers in the stack:
  ```bash
  docker stack ps dockercoins
  ```

]

---

class: btp-manual

## Specifics of stack deployment

Our apps are not *exactly* identical to the ones deployed with `docker service create`!

- Each stack gets its own overlay network by default

- Services of the task are connected to this network
  <br/>(unless specified differently in the Compose file)

- Services get network aliases matching their name in the Compose file
  <br/>(just like when Compose brings up an app specified in a v2 file)

- Services are explicitly named `<stack_name>_<service_name>`

- Services, tasks, and other objects get an label indicating which stack they belong to

---

## Maintaining multiple Stack environments

There are many ways to handle variations between environments

- You can deploy the same Compose YAML (Stack files) many times in the same Swarm

- Compose/Stack files can use environment variables

- Compose/Stack files can use YAML templating (as of v3.4)

- Check out the new Docker App CLI for The Next Generation™️  ([github.com/docker/app](https://github.com/docker/app))
  - Version Compose files like you version code releases
  - Store them in images on Docker Hub
  - Deploy them with envvars to Swarm

---

## docker-compose to Swarm workflow

Because of the common YAML file format, the dev-to-ops workflow is simpler

- docker-compose auto-loads `docker-compose.yml`, usually built just for dev

- Developers can use `docker-compose.override.yml` to change defaults above

- docker-compose and Swarm Stacks can load alternate file(s), or many files (layered)

- docker-compose and Swarm Stacks can use environment variables and templating

- docker-compose ignores any `deploy:` info and Stacks ignore any `build:` info

- docker-compose and Swarm Stacks can use the new docker-app CLI

---

## Good to know ...

- Compose file version 3 adds the `deploy` section

- Further versions (3.1, ...) add more features (secrets, configs ...)

- You can re-run `docker stack deploy` to update a stack

- You can make manual changes with `docker service update` ...

- ... But they will be wiped out each time you `docker stack deploy`

  (That's the intended behavior, when one thinks about it!)

