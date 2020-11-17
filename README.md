# Pros and Cons of using docker volume mount
This repo is just a pre-built setup where you can just compare whether volume mount build setup is suitable for your project or not.

## Setting things up
```bash
# Brings up the container
~/git/repo> docker-compose up 
Creating network "node_default" with the default driver
Creating node_node_1 ... done
Attaching to node_node_1
```

## Benchmarking the build setup
```bash
# Connecting to the bash process
~/git/repo> docker exec -ti container_id  bash

# Update the package.json based on your dependencies
root@4f968b99e802:/> mkdir /home/bench # create your custom directory
root@4f968b99e802:/> cp -r /app/* /home/bench/
root@4f968b99e802:/> cd /app
root@4f968b99e802:/app> npm install # Note down the completion time

root@4f968b99e802:/app> cd /home/bench
root@4f968b99e802:/home/bench> npm install # Note down the completion time

# Compare the times of both mounted version and non-mounted
# version and decide the build configuration.
```