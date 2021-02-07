---
title: getFileDirectory
category: Java
order: 1
---

Genera la ruta absoluta de un archivo a parir de su relación relativa con el ejecutable.

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

Salida (varía según el directorio y el sistema de archivos):
```
Ruta generada: E:\Root\Repos\Aplicativo\pdf\terminos-y-condiciones.pdf
```
