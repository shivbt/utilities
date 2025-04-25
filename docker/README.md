# Reclaiming Disk Space with Docker

If you're using Docker and want to free up disk space on your machine, the
following commands will help you clean up unused containers, volumes, images
, and more.

## 🧱 Containers

To remove unused (non-running) containers and reclaim space:

```bash
# List all containers (active and inactive)
docker container ls --all

# Remove all stopped (non-active) containers
docker rm $(docker ps --filter status=exited -q)

# Verify only active containers remain
docker container ls --all
```

## 📦 Volumes

Docker volumes can take up a significant amount of space over time. Here's
how to clean them up:

```bash
# List all volumes
docker volume ls

# Remove all unused (dangling) volumes
docker volume prune
```

## 🖼️ Images

To remove Docker images and free up space:

```bash
# List all Docker images
docker image ls

# Force remove all images (used and unused)
docker rmi -f $(docker images -aq)
```

> ⚠️ Be cautious: This will remove **all images**, including ones currently in use.


## 🛠️ `docker system` – All-in-One Cleanup

The `docker system` command is very useful to get system wide usage and reclaim
space in a snap (though it can not reclaim active components).

```bash
# Show disk usage by Docker components (just like linux df)
docker system df
```

**Sample Output:**
```
TYPE                TOTAL     ACTIVE    SIZE      RECLAIMABLE
Images              6         6         1.58GB    69.24MB (4%)
Containers          32        0         8.94GB    8.94GB (100%)
Local Volumes       33        33        4.73GB    0B (0%)
Build Cache         0         0         0B        0B
```

```bash
# Remove all unused data (images, containers, volumes, build cache)
docker system prune
```

**Warning:**
This will remove:
- All stopped containers  
- All unused networks  
- All dangling images  
- All dangling build cache  

You'll be prompted to confirm:
```
Are you sure you want to continue? [y/N]
```

---

## 🙏 Acknowledgement

- [The official: Docker Documentation](https://docs.docker.com/reference/cli/docker/)
- [Always helpful: Stack Overflow](https://stackoverflow.com/questions/44785585/how-can-i-delete-all-local-docker-images)
- [The AI one: ChatGPT](https://chatgpt.com/)
