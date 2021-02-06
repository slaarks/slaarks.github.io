---
title: getFileRoute(String file)
category: Java
order: 1
---

```bash
/
├── pdf/
│   ├── contrato-de-servicios.pdf
│   ├── terminos-y-condiciones.pdf
│   └── aviso-de-privacidad.pdf
└── aplicativo.jar
```
A veces nuestros aplicativos requieren de ciertos archivos para operar, y suele ser más práctico no empaquetarlos como parte del jar porque de esa forma no hay que reempaquetar cuando algún archivo se actualice. El problema es que para poder utilizar recursos externos, necesitamos conocer su ubicación en el sistema de ficheros, y muchas veces ni siquiera sabemos en dónde correrá nuestro aplicativo.

Para solucionar el problema anterior, te presento el siguiente truco que permite genrear las rutas absolutas de los archivos distribuídos junto con el jar:

```java
import java.io.File;
import java.io.IOException;

public class RandomMain {

	public static void main(String[] args) {
		
		String rutaGenerada = getFileRoute("pdf","terminos-y-condiciones.pdf");
		System.out.println("Ruta generada: " + rutaGenerada);

	}
	
	private static String getFileRoute(String folder, String file) {
		
		StringBuilder directory = new StringBuilder();

		try {
			directory.append(new File(".").getCanonicalFile().toString());
		} catch (IOException e) {
			e.printStackTrace();
		}

		directory.append(File.separator).append(folder);
		directory.append(File.separator).append(file);
		
		return directory.toString();
		
	}
}
```

Salida (depende del directorio y el sistema de archivos en el que se ejecute el aplicativo):
```
Ruta generada: E:\Root\Repos\Aplicativo\pdf\terminos-y-condiciones.pdf
```


Espero que esta técnica te sea de utilidad. ¡Hasta la próxima!
