---
title: create launcher
category: Linux
order: 1
---

- Mover la carpeta de la aplicacion a `/opt` (directorio de Linux para aplicaciones de terceros).
- Crear el archivo `NOMBRE_APP.desktop` dentro del directorio `/usr/share/applications`, con el siguiente contenido:

```bash
[Desktop Entry]
Type=Application
Categories=CATEGORÍAS;
Name=NOMBRE_VISIBLE
Exec=RUTA_EJECUTABLE
Icon=RUTA_ICONO
```

Ejemplo (launcher para Telegram):

ARCHIVO: `/usr/share/applications/Telegram.desktop`

```bash
[Desktop Entry]
Type=Application
Categories=Network;
Name=Telegram
Exec=/opt/Telegram/Telegram -- %u
Icon=/opt/Telegram/telegram.png
```