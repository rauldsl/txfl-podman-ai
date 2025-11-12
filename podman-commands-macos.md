# 🧱 Common Podman Commands (macOS)

A quick reference for the most commonly used **Podman commands** on macOS.  
Especially useful if you're coming from Docker.

---

## 🧱 Container Lifecycle

| Command | Description |
|----------|--------------|
| `podman pull <image>` | Download an image from a registry (like Docker Hub). |
| `podman images` | List all local images. |
| `podman run [options] <image>` | Create and start a container (e.g. `podman run -it --rm ubuntu bash`). |
| `podman ps` | Show running containers. |
| `podman ps -a` | Show all containers (including stopped ones). |
| `podman stop <container>` | Stop a running container. |
| `podman start <container>` | Start an existing container. |
| `podman restart <container>` | Restart a container. |
| `podman rm <container>` | Remove a stopped container. |
| `podman rmi <image>` | Remove an image. |

---

## 🧭 Inspection and Logs

| Command | Description |
|----------|--------------|
| `podman inspect <container or image>` | Show detailed info about a container or image. |
| `podman logs <container>` | Show logs of a container. |
| `podman top <container>` | Show running processes inside the container. |
| `podman stats` | Display resource usage (CPU, memory, etc.) of containers. |

---

## ⚙️ Building and Managing Images

| Command | Description |
|----------|--------------|
| `podman build -t <name> .` | Build an image from a Dockerfile. |
| `podman tag <image> <newname>` | Tag an image. |
| `podman push <image>` | Push an image to a remote registry. |

---

## 🧩 Pod Management

| Command | Description |
|----------|--------------|
| `podman pod create --name <pod>` | Create a new pod. |
| `podman pod ps` | List running pods. |
| `podman pod stop <pod>` | Stop a pod. |
| `podman pod rm <pod>` | Remove a pod. |

---

## 🛠️ Utilities

| Command | Description |
|----------|--------------|
| `podman exec -it <container> <cmd>` | Run a command inside a running container. |
| `podman cp <container>:<path> <local_path>` | Copy files from container to host (or vice versa). |
| `podman system prune` | Remove all unused data (containers, images, volumes). |
| `podman info` | Display system information. |
| `podman machine list` | Show available Podman virtual machines (on macOS/Windows). |
| `podman machine start` / `stop` | Start or stop the Podman VM (required to run containers). |

---

## 🔥 Example Workflow (macOS)

```bash
podman machine init           # Create the Podman VM
podman machine start          # Start the VM
podman pull alpine            # Pull a test image
podman run -it alpine sh      # Run a container
podman ps                     # Check running containers
podman stop <container>       # Stop it
podman rm <container>         # Clean up
podman system prune           # Free unused space
```

---

## 🧾 Notes

- Podman commands are nearly identical to Docker commands, so switching is easy.
- On macOS, Podman runs inside a lightweight virtual machine (using `podman machine`).
