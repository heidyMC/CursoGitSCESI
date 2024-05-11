# Curso Git SCESI

## CLASE 1:

### ¿Qué es un control de versiones?

Un control de versiones registra cada cambio en el código fuente de un proyecto, lo que proporciona un historial completo de las modificaciones, incluyendo quién las hizo y cuándo se realizaron.
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

Git es un sistema que guarda una copia de todo tu proyecto en tu computadora y en la de tus compañeros, permitiendo registrar los cambios que realizas y sincronizarlos.

### ¿Qué es un repositorio?
Es una carpeta donde guardas todos los archivos de tu proyecto  también guarda un registro de todos los cambios que haces en esos archivos a medida que trabajas en tu proyecto. 

Para crear un repositorio local puedes usar el comando:

1. $ git init `<indicando el nombre del proyecto>` -> creara una carpeta configurada y vacía con el nombre indicado anteriormente


Para iniciar en un repositorio de una carpeta ya existente puedes usar el comando git init dentro de la raíz del directorio del proyecto

2. $ git init `<nuevo-proyecto>` -> para inicializar

3. $ cd `<directorio del proyecto que ya existe>`

En ambos casos se creara una rama principal de tu proyecto por defecto y es la que se usara para trabajar

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