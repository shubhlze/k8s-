🚢 1️⃣ Client
Commands you run:

docker build — create image from Dockerfile

docker push — upload image to Registry

docker pull — download image from Registry

docker run — start a container from image

Client talks to the Docker Daemon.

🧠 2️⃣ Docker Daemon (dockerd)
The main engine.

Builds, runs, and manages:

Images (templates)

Containers (running processes)

Networks (how containers communicate)

Volumes (persistent storage)

🗂️ 3️⃣ Images
Blueprints to create containers.

Built from Dockerfiles.

Stored locally or in Registry.

Examples: nginx, Redis, MongoDB.

📦 4️⃣ Containers
Running instances of images.

Isolated mini-environments.

Share the host’s OS but act like independent machines.

🏢 5️⃣ Registry
Remote storage for images.

Public: Docker Hub.

Private: AWS ECR, GCP Container Registry.

You push/pull images here.

🔀 6️⃣ Docker Networking (Added!)
📡 What is it?
Controls how containers talk:

To each other

To the host

To the internet

🗃️ Types of Networks:
Network	What it means	Use case
Bridge (default) -	Private internal network on your machine	Connect containers together
Host	- Container uses host’s network directly	Max performance, no extra network
None -	No network	Fully isolated
Overlay	- Virtual network connecting containers across multiple hosts	Swarm, Kubernetes
Macvlan -	Give container its own IP on local LAN	Legacy systems, special cases

✅ Key:

Bridge: Most common.

Overlay: Used in clusters.

Host: For speed.

None: For isolation.

Macvlan: For advanced networking.

🔑 How Networking Fits In:
✔ When you run a container:

Docker attaches it to a network (default: bridge)

You can specify a custom network.

Containers on the same network can talk by container name.

✔ Use docker network ls to see networks.

✔ Use docker network create to make custom networks.

⚡ 🗂️ Summary Cheat Code
Flow	What happens
1. Build	docker build → Daemon → Image
2. Push	docker push → Registry
3. Pull	docker pull ← Registry
4. Run	docker run → Daemon → Container
5. Networking	Container connects to network (bridge/host/overlay/etc.)

✅ Your Learning Mantra
Dockerfile → Image → Registry → Container → Network

📌 Bonus Command Tips
bash
Copy
Edit
docker network ls          # List networks
docker network inspect     # Details about a network
docker network create mynet  # Create a custom network
docker run --network=mynet ...  # Run container on custom network
