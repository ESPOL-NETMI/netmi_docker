# Config dev environment 🛠

## **[Stage 1]** .- Cloning repositories

**Step 1.- Go to environment dir**

**Step 2.- Cloning all repositories**

_Dockerfiles_

```bash
git clone https://github.com/ESPOL-APINM/netmi_docker.git
```

_Backend_

```bash
git clone https://github.com/ESPOL-APINM/netmi_backend.git
```

_Frontend_

```bash
git clone https://github.com/ESPOL-APINM/netmi_frontend.git
```

## **[Stage 2]**.- Run dockerized environment

**Step 1.- Go to "netmi_docker" directory**

```bash
cd netmi_docker/
```

**Step 2.- Build docker environment and your containers**

```bash
docker-compose up --build -d
```

# Authors ✒

- **Maria Aguilar Carolina Alvarado** - ✉ *macaagui@espol.edu.ec* - [mcarolina3101](https://github.com/mcarolina3101)
- **Alex Alberto Córdova Balón** - ✉ *alealcor@espol.edu.ec* - [alealcor](https://github.com/alealcor)
