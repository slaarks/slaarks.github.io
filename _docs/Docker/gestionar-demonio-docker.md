---
title: Gestionar el demonio de docker
category: Docker
order: 1
---

Revisar el estado del demonio de docker:
```bash
systemctl status docker
```

Iniciar el demonio de docker:
```bash
systemctl start docker
```

Detener el demonio de docker:
```bash
systemctl stop docker
```

Arrancar el demonio de docker junto con el sistema:
```bash
systemctl enable docker
```
