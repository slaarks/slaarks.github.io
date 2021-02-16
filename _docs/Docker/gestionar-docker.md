---
title: Gestionar docker
category: Docker
order: 1
---

| USO | COMANDO |
|---|---|
| Versión de docker | `docker version` |
| Detalles del docker instalad | `docker info` |
| Estado del demonio de docker | `systemctl status docker` |
| Iniciar del demonio de docker | `systemctl start docker` |
| Detener del demonio de docker | `systemctl stop docker` |
| Iniciar del demonio de docker con el sistema | `systemctl enable docker` |


Ejecutar comandos docker sin sudo:
```bash
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
```
