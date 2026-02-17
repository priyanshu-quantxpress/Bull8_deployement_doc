# Setting Up Blitz-GateWay

Since the target Linux machine does not have internet access, the Docker image is first built on a Windows machine with internet connectivity, exported as a portable tar file, and then transferred to the Linux server for deployment.

The setup covers building the Docker image, transferring it securely, loading it into the Linux Docker environment, configuring Docker Compose, and running the service as a containerized application. This approach ensures consistent deployments across environments while maintaining isolation, portability, and ease of maintenance.

By following this process, Blitz Gateway can be reliably deployed, restarted, and managed on restricted or secure infrastructure without requiring direct internet access.

# Part 1: Build Docker Image on Windows

### Step 1 — Go to Blitz Gateway Source Code

On Windows (PowerShell / CMD):

```bash
cd <path-to-blitz-gateway-project>
```

You must have:

- `Dockerfile`
- Application source code
- Config files (if any)

---

### Step 2 — Build Docker Image

```bash
docker build -t blitz-gateway:latest .
```

Verify image:

```bash
docker images | grep blitz-gateway
```

---

### Step 3 — Save Image as TAR File

```bash
docker save blitz-gateway:latest -o blitz-gateway_latest.tar
```

This file is portable and can be used offline.

---

## Part 2: Transfer Image to Linux Machine

### Step 4 — Copy Image to Linux

Using **WinSCP**, copy:

```
blitz-gateway_latest.tar
```

To Linux path:

```
/opt/apps/
```

---

## Part 3: Load Image on Linux

### Step 5 — Login to Linux Server

```bash
cd /opt/apps
ls
```

You should see:

```
blitz-gateway_latest.tar
```

---

### Step 6 — Load Docker Image

```bash
docker load -i blitz-gateway_latest.tar
```

Verify:

```bash
docker images | grep blitz-gateway
```

Expected output:

```
blitz-gateway   latest
```

---

## Part 4: Docker Compose Setup

### Step 7 — Place Docker Compose File

Ensure the following file exists:

```
/opt/apps/docker-compose.yml
```

Example (simplified):

```yaml
version: "3.8"

services:
  blitz-gateway:
    image: blitz-gateway:latest
    container_name: blitz_gateway
    restart: always
    ports:
      - "8080:8080"
    env_file:
      - .env
    networks:
      - blitz-network

networks:
  blitz-network:
    driver: bridge
```

> ⚠️ Image name must **exactly match** the loaded image (`blitz-gateway:latest`)
> 

---

## Part 5: Run Blitz Gateway

### Step 8 — Start the Service

```bash
docker-compose up -d
```

---

### Step 9 — Verify Container

```bash
docker ps | grep blitz_gateway
```

Expected output:

```
Up ... blitz_gateway
```

---

## Part 6: Validate Gateway

### Check Logs

```bash
docker logs -f blitz_gateway
```
