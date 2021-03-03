---
title: gestionar docker
category: Docker
order: 1
---

| USO | COMANDO |
|---|---|
| Versión de docker | `docker version` |
| Detalles del docker instalado | `docker info` |
| Estado del demonio de docker | `systemctl status docker` |
| Iniciar el demonio de docker | `systemctl start docker` |
| Detener el demonio de docker | `systemctl stop docker` |
| Iniciar el demonio de docker junto con el sistema | `systemctl enable docker` |


Ejecutar comandos docker sin sudo:
```bash
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```
