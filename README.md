# Curso Git SCESI

## CLASE 1:

### ¿Qué es un control de versiones?

>Un control de versiones registra cada cambio en el código fuente de un proyecto, lo que proporciona un historial completo de las modificaciones, incluyendo quién las hizo y cuándo se realizaron.
Un control de versiones es importante por que:

* Rendimiento, solo se guarda lo necesario
* Seguridad, conserva toda accion 
* Flexibilidad, no es necesario un desarrollo lineal

### Historia

* 1990 -> Nace CVS que es el primer control de versiones
* 2005 -> Se crea git
* 2008 -> Se crea github
* 2018 -> Microsoft compra Github
* 2024 -> Git domina el mercado

### ¿Qué es git?

>Git es un sistema que guarda una copia de todo tu proyecto en tu computadora y en la de tus compañeros, permitiendo registrar los cambios que realizas y sincronizarlos.

### ¿Qué es un repositorio?
>Es una carpeta donde guardas todos los archivos de tu proyecto  también guarda un registro de todos los cambios que haces en esos archivos a medida que trabajas en tu proyecto. 

* Para crear un repositorio local puedes usar el comando:

1. $ git init `<indicando el nombre del proyecto>` -> creara una carpeta configurada y vacía con el nombre indicado anteriormente

~~~
Para iniciar en un repositorio de una carpeta ya existente puedes usar el comando git init dentro de la raíz del directorio del proyecto
~~~
2. $ git init `<nuevo-proyecto>` -> para inicializar

3. $ cd `<directorio del proyecto que ya existe>`
~~~
En ambos casos se creara una rama principal de tu proyecto por defecto y es la que se usara para trabajar
~~~
### States y commits:
Los 3 estados de de git 

***Modified:*** Es cuando el archivo se ha creado, modificado o eliminado.

***Starged:*** Se marca el archivo para ser confirmado es transitorio.

***Commited:*** El archivo se encuentra grabado en el repositorio local.
1. `$ git  status` -> para ver el estado del archivo y en que 2.estado se envuentra
2. `$ git add` -> permite agregar un archivo
3. `$ git commit ` -> registra los cambios realizados en el directorio de trabajo en un nuevo commit en el repositorio local
4.  `$ git add` -> agrega cambios
5. $ `git  restore` -> restaura archivos

### ¿Qué es un commit?
>Los commits sirven para registrar los cambios(que tienes en el área de staging) que se han producido en el repositorio y es una pieza fundamental, para hacer commit se usa los comandos:

1. `$ git commit` -> creara un nuevo commit en tu repositorio y añadira referencia al commit en la rama que estas trabajando.
2. `$ git commit -m "escribe tu modificación aqui"` ->  para añadir directamente un mensaje sin abrir el editor.
3. `$ git commit --amend -m "texto ahi"` ->   permite reescribir un commit.
4. `$ git log` -> permite ver el historial de commits hechos.

### ¿Qué es el head? 
>Es como un marcador que indica la versión o rama actual en la que estás trabajando en tu repositorio.
* Para deshacer un archivo modificado: 
  1. `$ git checkout <código commit>` -> para cambiar entre ramas o para restaurar archivos a una versión anterior

  2. `$ git restore index.html` -> restaura el archivo index.html
  3. `$ git restore` -> restaura todo el directorio de trabajo
  4. `$ git restore '*.js'` -> restaura todos los archivos terminados en *.js

## CLASE 2:
### ¿Qué es una rama?
>Una rama en un repositorio es como una copia separada de los archivos. En un equipo, cada persona puede trabajar en su propia copia sin interferir con los demás. Una vez que terminan, pueden combinar sus cambios con la versión principal de los archivos.

1. `$ git branch` -> para listar las ramas que existen.
2. `$ git branch <nombre de la rama>` -> para crear una rama
2. `$ git switch <nombre de la rama>` ->para cambiarse de rama
3. `$ git checkout <nombre de la rama>` -> otra manera de cambiarse de rama
4. `$ git checkout -b <nombre de la rama>` -> cambia de rama y además crea una nueva

**Fusionando ramas:**

1. `$ git merge <nombre rama>` ->para incorporar los cambios de una rama a la rama en la que nos encontramos
2. `$ git merge --edit` -> abre el editor antes de hacer el commit
3. `$ git merge --no-commit` -> evita que haga commit automaticamente

**Elimar ramas ¿por que?**

>Por que es una buena practica, además que las ramas tiene un propósito único y  corto de periodo 
1. `$ git branch -d <nombre de la rama>` -> borra ramas fusionadas
2. `$ git branch -a` -> permite visualizar todas las ramas
* Dato extra:
3. `$ git log --oneline`  -> muestra los títulos de los commits 
4. `$ git log --graph` -> muestra el historial de commits de tu repositorio.

## CLASE 3:
### Repositorios remotos:
>Los repositorios remotos son versiones de tu proyecto que están alojadas en un servidor en línea estos repositorios permiten colaborar con otras personas en el desarrollo del proyecto, sincronizar tus cambios con otros miembros del equipo y hacer copias de seguridad de tu código.
1. `$ git remote add origin` <url_de_tu_repositorio_remoto> -> para enlazar el repositorio local con el remoto
2. `git push origin main` -> se usa para enviar tus cambios locales desde tu rama principal a un repositorio en línea llamado "origin".

**Clonando un repositorio remoto creado previamente:**

1. `$ git clone <url de tu repositorio>` -> para clonar un repositorio remoto.

**Eliminar ramas del repositorio local que no se usan**

1. `$ git fetch` -> se utiliza para recuperar todos los cambios del repositorio remoto a tu repositorio local.
2. `$ git remote prune origin` ->  se utiliza para eliminar referencias locales a ramas remotas que ya no existen en el repositorio remoto llamado "origin".

## CLASE 4:
### Push, pull y pull request
**Push:**
Se utiliza para enviar tus cambios locales al repositorio remoto

* `$ git push origin <rama>`

**Pull:**
Nos sirve para descargar los cambios o modificaciones del repositorio remoto al repositorio local
* `$ git pull origin <rama>`

**pull request:**
Es una petición de cambios que se
envía al repositorio original.

## CLASE 5:

### Git Flow
>Usa diferentes tipos de ramas para manejar características, correcciones y lanzamientos, manteniendo todo ordenado y colaborativo.

**Ramas principales**
* main o master: Su proposito es contener el código de producción (rama principal) 
* develop: código de pre-producción que incluye nuevas características que aún no han sido probadas y validadas, pero que están destinadas a ser lanzadas en la próxima versión de producción.
* feature: Cuando trabajas en una nueva característica para el proyecto.
* realese: cambios de ultimo momento
* hotfix: parches o arreglar bugs pequeño (parte del main)

**GitHub Flow**
>Es una metodología de trabajo en Git que se basa en el uso de ramas para desarrollar nuevas funciones y corregir errores. Consiste en cuatro pasos: crear una rama, agregar commits, abrir una solicitud de extracción para revisión y fusión de los cambios. Este enfoque permite un desarrollo ágil y colaborativo.

**Tipos de rama**
* Rama main y cualquier otra rama que quiera ser integrada por medio de una pull.

**Trunk Based Development:**
>Se basa en trabajar directamente en la rama principal del repositorio, promoviendo cambios frecuentes y pequeños para facilitar la integración continua y la entrega rápida de nuevas características.
* **Beneficios:**
1. Integracion continua y menos friccion
2. Menos trabajo manual
3. Despliegue a produccion continuo

