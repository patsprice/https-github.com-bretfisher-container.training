# Updating services

- We want to make changes to the web UI

- The process in the Real World is as follows:

  - edit code

  - build new image

  - ship new image to registry

  - deploy (run) new image

Today we're just going to use different image versions that were pre-built

---

## Updating a single service with `service update`

- To update a single service, we could do the following:
  ```bash
  docker service update dockercoins_webui --image dogvscat/webui:v0.2
  ```

- Make sure to tag properly your images: update the `TAG` at each iteration

  (When you check which images are running, you want these tags to be uniquely identifiable)

---

## Updating services with `stack deploy`

- With Stacks, all we have to do is edit the stack file and update the version, then:
  ```bash
  docker stack deploy -c composefile.yml nameofstack
  ```
--

- That's exactly what we used earlier to deploy the app

- We don't need to learn new commands!

- It will diff each service and only update ones that changed

--

- For automation, set environment variables for each image tag and then:
  ```bash
  export WEBUI_TAG=v0.2
  docker stack deploy -c composefile.yml nameofstack
  ```

---

## Deploy our changes

- Let's make the numbers on the Y axis bigger!

- We need to deploy `dogvscat/webui:v0.2`

.exercise[

- Build, ship, and run:
  ```bash
  export TAG=v0.2
  docker stack deploy -c dockercoins.yml dockercoins
  ```

]

- Because we're tagging all images in this demo v0.2, deploy will update all apps, FYI

---

## Viewing our changes

- Wait at least 10 seconds (for the new version to be pulled and deployed)

- Then reload the web UI

- Or just mash "reload" frantically

- ... Eventually the legend on the left will be bigger!
