<div style="text-align: center;">
    <h1>Actividad Evaluable 2</h1><br>
    <h2>Control de versiones</h2><br>
    <h3>Despliegue de Aplicaciones Web - DAW Distancia<br>
    CIFP Sect. Industrial y Servicios - La Laboral<br>
    Curso 2024-2025<br>
    08 de febrero de 2025<br>
    Emilio Zaera Vidal - 46.911.234-C</h3>
</div>



<div style="page-break-after: always;"></div>
> Autor: **Emilio Zaera Vidal** 
>
> fecha: 08 del 02 de 2025
[TOC]

## 1. Objetivo

La actividad tiene como propósito adquirir experiencia práctica en el uso de Git para el control de versiones en un entorno de desarrollo. A través de la resolución de ejercicios, se busca que el alumno aprenda a trabajar tanto en local como en remoto, utilizando herramientas como la línea de comandos y *SourceTree*, además de gestionar ramas, resolver conflictos y documentar correctamente su flujo de trabajo.

---

---



## 2. Metodología

La tarea se divide en varios apartados. Primero, se realizan operaciones básicas en un repositorio Git local, incluyendo la inicialización, creación de ramas, commits y fusiones. Luego, se trabaja con un repositorio remoto en GitHub a través de SourceTree, subiendo cambios y sincronizando ramas. También se abordan la gestión de conflictos y la subida de documentación al repositorio. Finalmente, se requiere la entrega de un informe en PDF con capturas de pantalla y un videoclip demostrativo que evidencie el desarrollo de la actividad y la identidad del estudiante.

---

---



## 3. Trabajo en local

> Esta parte se resolverá con comandos.

Antes de comenzar el trabajo, escribo este comando para que el historial de ramas de Git se mantenga como un árbol: 

```bash
$ git config --global merge.ff false
```

<img src="./documento.assets/image-20250208095021384.png" alt="image-20250208095021384" style="zoom:50%;" />

---



### Cuestión 1

**Enunciado**

Inicializa un nuevo repositorio Git en una carpeta llamada `"labdist"` y agrega los archivos proporcionados  en el aula virtual. Renombra la rama master a `main` , si es necesario. Realiza el primer commit. Muestra el log del repositorio.

**Bloques de código y capturas de pantalla**

```bash
git init
git branch -m master main
git add .
git commit -m "Archivos agregados y renombrado master -> main"
git log
```

<img src="./documento.assets/image-20250208095858809.png" alt="image-20250208095858809" style="zoom:50%;" />

<img src="./documento.assets/image-20250208095948181.png" alt="image-20250208095948181" style="zoom:50%;" />

<img src="./documento.assets/image-20250208100045588.png" alt="image-20250208100045588" style="zoom:50%;" />

---



### Cuestión 2

**Enunciado**

Incluye un fichero `.gitignore` para que los ficheros README.md , LICENCE.txt y passwords.txt sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.

**Bloques de código y capturas de pantalla**

<img src="./documento.assets/image-20250208100852841.png" alt="image-20250208100852841" style="zoom:50%;" />



```bash
git add .
git commit -m "Incluido fichero .gitignore"
git log --oneline
git diff head~1..head
```

<img src="./documento.assets/image-20250208125717750.png" alt="image-20250208125717750" style="zoom:30%;" />

---



### Cuestión 3

**Enunciado**

En el repositorio, crea los archivos `README.md` , `LICENCE.txt` y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos ignorados.

**Bloques de código y capturas de pantalla**

<img src="./documento.assets/image-20250208123217642.png" alt="image-20250208123217642" style="zoom:50%;" />

```bash
git status
```

<img src="./documento.assets/image-20250208123518720.png" alt="image-20250208123518720" style="zoom:50%;" />

> No hay nada pendiente de añadir al staging area porque esos ficheros son ignorados



```
git status --ignored
```

<img src="./documento.assets/image-20250208123738134.png" alt="image-20250208123738134" style="zoom:50%;" />

---



### Cuestión 4

**Enunciado**

Crea una rama `feature-estilos`. Cámbiate a ella.

- Modifica el archivo `estilos.css`:

  - propiedad color del `body` y de `h2`: `#2a2a2a`

  - propiedad `background-color` de `header` y `footer`: `#2a75ff`

- Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje "actualizados estilos a azules".

**Bloques de código y capturas de pantalla**

```bash
git branch feature-estilos
git checkout feature-estilos
git status
git add .
git commit -m "actualizados estilos a azules"
```

![image-20250208130700934](./documento.assets/image-20250208130700934.png)

---



### Cuestión 5

**Enunciado**

Vuelve a la rama `main` . En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje 'añadido autor en index'. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'.

**Bloques de código y capturas de pantalla**

```bash
git checkout main
```

<img src="./documento.assets/image-20250208130950738.png" alt="image-20250208130950738" style="zoom:50%;" />

```
git status
git add .
git commit -m "añadido autor en index"
git log --graph -oneline --decorate
```

<img src="./documento.assets/image-20250208131359961.png" alt="image-20250208131359961" style="zoom: 33%;" />

---



### Cuestión 6

**Enunciado**

Fusiona la rama `feature-estilos` en la rama `main`. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

**Bloques de código y capturas de pantalla**

```bash
git status
git merge feature-estilos
git log --graph --oneline --decorate
```

<img src="./documento.assets/image-20250208131856109.png" alt="image-20250208131856109" style="zoom: 33%;" />

---

---



## 4. Trabajo en remoto

### Cuestión 1

**Enunciado**

Continúa con el repositorio `labdist` . Añade el repositorio a ***Sourcetree***.  

**Bloques de código y capturas de pantalla**

<img src="./documento.assets/image-20250208133639326.png" alt="image-20250208133639326" style="zoom:33%;" />

<img src="./documento.assets/image-20250208140620965.png" alt="image-20250208140620965" style="zoom:50%;" />

---



### Cuestión 2

**Enunciado**

En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir todas las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub.

**Capturas de pantalla**

<img src="./documento.assets/image-20250208133947565.png" alt="image-20250208133947565" style="zoom:50%;" />

<img src="./documento.assets/image-20250208134007803.png" alt="image-20250208134007803" style="zoom:50%;" />

En *SourceTree* añado el remoto:



<img src="./documento.assets/image-20250208135949590.png" alt="image-20250208135949590" style="zoom:50%;" />

<img src="./documento.assets/image-20250208140802003.png" alt="image-20250208140802003" style="zoom:50%;" />

Subo (push) todas las ramas al remoto:

<img src="./documento.assets/image-20250208140825697.png" alt="image-20250208140825697" style="zoom:50%;" />



<img src="./documento.assets/image-20250208134544993.png" alt="image-20250208134544993" style="zoom: 33%;" />

---



### Cuestión 3

**Enunciado**

En el repositorio **local**, crea una rama `feature-index` . Añade el siguiente código dentro de la `<section class="about">` .

```html
<h2>Conoce a Nuestro Equipo</h2>
<p>
    labdist está formado por un equipo de diseñadores y
    desarrolladores apasionados que trabajan juntos para ofrecer soluciones
	tecnológicas de alta calidad. Cada miembro de nuestro equipo aporta
	experiencia en diseño, programación, y soporte técnico, asegurando que
	nuestros clientes reciban un servicio completo y personalizado.
<p>
<p>
    Nuestro objetivo es que cada cliente se sienta acompañado en su
	aventura digital, con un equipo profesional que entiende sus necesidades y
	trabaja para hacer crecer su presencia en línea.
</p>
```

Añade los cambios y crea un commit con el mensaje "Añadido párrafo equipo en index.html". Sube los cambios al remoto. (Recuerda que debes usar SourceTree en todo este apartado).

**Capturas de pantalla**

Pincho en el icono Branch:

<img src="./documento.assets/image-20250208140956869.png" alt="image-20250208140956869" style="zoom:50%;" />

Le doy un nombre a la nueva rama y pincho en Create Branch:

<img src="./documento.assets/image-20250208141048918.png" alt="image-20250208141048918" style="zoom:50%;" />

Puedo ver la nueva rama:

![image-20250208141240748](./documento.assets/image-20250208141240748.png)

Agrego código a `index.html`:

<img src="./documento.assets/image-20250208163416074.png" alt="image-20250208163416074" style="zoom:30%;" />



Añado los cambios al staging area:

<img src="./documento.assets/image-20250208141653836.png" alt="image-20250208141653836" style="zoom:50%;" />

<img src="./documento.assets/image-20250208141711997.png" alt="image-20250208141711997" style="zoom:50%;" />

Para hacer el commit pincho en su icono:

<img src="./documento.assets/image-20250208141737006.png" alt="image-20250208141737006" style="zoom:50%;" />

Añado el comentario y pulso el botón "Commit".

![image-20250208141947548](./documento.assets/image-20250208141947548.png)

Veo el resultado:

<img src="./documento.assets/image-20250208142010562.png" alt="image-20250208142010562" style="zoom:70%;" />

Subo los cambios al remoto (push):

<img src="./documento.assets/image-20250208142058179.png" alt="image-20250208142058179" style="zoom:50%;" />

En GitHub veo lo siguiente:

<img src="./documento.assets/image-20250208142302569.png" alt="image-20250208142302569" style="zoom:40%;" />

---



### Cuestión 4

**Enunciado**

En el repositorio local, fusiona la rama `feature-index` en la rama `main` .  

**Capturas de pantalla**

Primero me coloco en la rama `main`:

<img src="./documento.assets/image-20250208142546236.png" alt="image-20250208142546236" style="zoom:70%;" />

Selecciono la rama `main` botón derecho en la rama `feature-index` y pulso sobre merge

<img src="./documento.assets/image-20250208164303721.png" alt="image-20250208164303721" style="zoom:50%;" />

<img src="./documento.assets/image-20250208142921082.png" alt="image-20250208142921082" style="zoom:50%;" />

---



### Cuestión 5

**Enunciado**

Edita el fichero `contacto.html`. Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit.

**Capturas de pantalla**

Muestro los ficheros con cambios pendientes y las diferencias:

![image-20250208143544704](./documento.assets/image-20250208143544704.png)

Añado los cambios:

<img src="./documento.assets/image-20250208143632520.png" alt="image-20250208143632520" style="zoom:70%;" />

Hago el commit:

![image-20250208143815133](./documento.assets/image-20250208143815133.png)

---



### Cuestión 6

**Enunciado**

Te das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (Asegúrate de que el fichero contacto.html ha recuperado todas las líneas borradas y no hay cambios pendientes en el repositorio.)

**Capturas de pantalla**

<img src="./documento.assets/image-20250208164956520.png" alt="image-20250208164956520" style="zoom:50%;" />

Hago hard reset:

<img src="./documento.assets/image-20250208165110036.png" alt="image-20250208165110036" style="zoom:50%;" />

No hay cambios pendientes:

![image-20250208144956237](./documento.assets/image-20250208144956237.png)

El fichero `index.html` vuelve a tener el `footer`:

<img src="./documento.assets/image-20250208165343266.png" alt="image-20250208165343266" style="zoom:33%;" />

---



### Cuestión 7

**Enunciado**

Crea una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo `contacto.html`:

```html
<section class="map">
	<h2>Nuestra Ubicación</h2>
	<p>C/Luis Moya 335, Gijón, Asturias</p>
	<iframe src="https://www.google.com/maps?
			q=C%2FLuis%20Moya%20335%2C%20Gij%C3%B3n%2C%20Asturias&output=embed"
			width="600" height="450" style="border:0;" allowfullscreen=""
			loading="lazy">
    </iframe>
</section>
```

 Añade los cambios. Realiza un commit.

**Capturas de pantalla**

Creo la rama y me cambio a ella:

<img src="./documento.assets/image-20250208150143541.png" alt="image-20250208150143541" style="zoom:50%;" />

Incluyo el código:

<img src="./documento.assets/image-20250208150425511.png" alt="image-20250208150425511" style="zoom:30%;" />

Añado los cambios:

<img src="./documento.assets/image-20250208150508863.png" alt="image-20250208150508863" style="zoom:60%;" />

Realizo el commit: 

<img src="./documento.assets/image-20250208150640147.png" alt="image-20250208150640147" style="zoom:50%;" />

Veo el resultado:

<img src="./documento.assets/image-20250208150703972.png" alt="image-20250208150703972" style="zoom:70%;" />

---



### Cuestión 8

**Enunciado**

Sube los cambios al remoto - los de todas las ramas. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`.

**Capturas de pantalla**

Subo los cambios al remoto (push):

<img src="./documento.assets/image-20250208151131515.png" alt="image-20250208151131515" style="zoom:40%;" />

Muestro en el remoto los cambios:

<img src="./documento.assets/image-20250208151549238.png" alt="image-20250208151549238" style="zoom:40%;" />

![image-20250208151721019](./documento.assets/image-20250208151721019.png)

---



### Cuestión 9

**Enunciado**

En GitHub, en la rama `main` , fusiona la rama `feature-mapa`. Baja los cambios del remoto a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde se vea la página principal de tu repositorio remoto.

**Capturas de pantalla**

> haré un Pull Request simulando una revisión del código antes de fusionarlo.
>
> Podría hacerse alternativamente de manera manual desde la pestaña "Branches"

![image-20250208152215652](./documento.assets/image-20250208152215652.png)

<img src="./documento.assets/image-20250208152341064.png" alt="image-20250208152341064" style="zoom:30%;" />

Me aparece una notificación de 1 Pull request pendiente:

<img src="./documento.assets/image-20250208152802511.png" alt="image-20250208152802511" style="zoom:50%;" />

Pulso en Merge y confirmo:

<img src="./documento.assets/image-20250208152906009.png" alt="image-20250208152906009" style="zoom:50%;" />

Hago un pull  para tenerlo en el repo local y verlo en *SourceTree*:

<img src="./documento.assets/image-20250208171108193.png" alt="image-20250208171108193" style="zoom:50%;" />

---

---



## 5. Conflictos

### Cuestión 1

**Enunciado**

Crea una rama `hotfix-js` . Cámbiate a ella. Añade este código en el fichero `script.js`:

```javascript
if (mensaje.value.trim() === "") {
	alert("Por favor, ingrese un mensaje.");
	valid = false;
}
```

Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js". *(Fíjate en los números de línea de tu editor...)*

**Capturas de pantalla**

Creo la rama nueva:

<img src="./documento.assets/image-20250208153834769.png" alt="image-20250208153834769" style="zoom:50%;" />

Modifico el código en VSC:

<img src="./documento.assets/image-20250208155257666.png" alt="image-20250208155257666" style="zoom:30%;" />

Añado los cambios:

<img src="./documento.assets/image-20250208155348001.png" alt="image-20250208155348001" style="zoom:50%;" />

Hago el commit con mensaje:

<img src="./documento.assets/image-20250208155455583.png" alt="image-20250208155455583" style="zoom:50%;" />

---



### Cuestión 2

**Enunciado**

Vuelve a la rama `main`. En el fichero `script.js` en las mismas líneas que en la cuestión anterior, añade el código siguiente:

```javascript
if (mensaje.value.trim() === "") {
	alert("Ingrese un mensaje, por favor");
	valid = false;
}
```

Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js rama main".  

**Capturas de pantalla**

Añado el cambio:

<img src="./documento.assets/image-20250208160135052.png" alt="image-20250208160135052" style="zoom:50%;" />

Hago commit:

![image-20250208160255039](./documento.assets/image-20250208160255039.png)

---



### Cuestión 3

**Enunciado**

Fusiona la rama `hotfix-js` en `main`. Debe producirse un conflicto. Resuélvelo como consideres oportuno. Cuando termines la resolución del conflicto sube los cambios al remoto.

**Capturas de pantalla**

Intento el merge de `hotfix-js` en `main`

> Obsérvese que tengo que tener la rama main seleccionada (doble clic, paso 1)

<img src="./documento.assets/image-20250208173018292.png" alt="image-20250208173018292" style="zoom:50%;" />

Me aparece el mensaje de **conflicto**:

<img src="./documento.assets/image-20250208173207454.png" alt="image-20250208173207454" style="zoom:50%;" />

> Mientras no resuelva el conflicto aparece Uncommitted changes

![image-20250208173659423](./documento.assets/image-20250208173659423.png)

Voy a resolver usando de manera manual, en Notepad++:

<img src="./documento.assets/image-20250208174928086.png" alt="image-20250208174928086" style="zoom:33%;" />

Manualmente lo dejo así:

<img src="./documento.assets/image-20250208174459340.png" alt="image-20250208174459340" style="zoom:33%;" />

Guardo y cierro el fichero y vuelvo a *SourceTree* , donde selecciono "Marcar como resuelto":

<img src="./documento.assets/image-20250208175218577.png" alt="image-20250208175218577" style="zoom:45%;" />

A continuación hago el commit para registrar los cambios y los subo al remoto:

<img src="./documento.assets/image-20250208175415676.png" alt="image-20250208175415676" style="zoom:50%;" />

<img src="./documento.assets/image-20250208175614648.png" alt="image-20250208175614648" style="zoom:45%;" />

Historial resultado:

![image-20250208175646909](./documento.assets/image-20250208175646909.png)

---

---



## 6. URL de mi repo en GitHub

https://github.com/ezveducastur/labdist

---

---



## 7. URL de mi videoclip

https://emiliozv.synology.me:5001/d/s/1261i8bARz0nYBTcmqXisnELR6q7GXcr/QVpsYUu-S0p9xiKCHLTPbxiudOhOjtJE-_bvgbFGnCgw
