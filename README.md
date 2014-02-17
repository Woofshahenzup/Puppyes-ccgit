Puppyes-ccgit
=============

Guia para mortales, configura y clona repositorios de git en PuppyLinux

La perspectiva de un usuario comun y corriente sin poderes mutantes.
¿Pero cual es la idea de usar git para gestionar un proyecto ya sea personal o 
grupal?, bueno veamos algunas ventajas.

- Se puede trabajar en el proyecto incluso sin una conexion a internet
- Es mas rápido desarrollar proyectos.
- Se puede saber quien ha tocado qué y cuándo el código.
- Se puede volver atras de forma rápìda.
- Puede controlar las versiones a tavés de etiquetas.  
- Mejora nuestra capacidad de trabajar en equipo.

La forma practica de usar git en Puppy
======================================

Lo primero que debemos hacer es:
- Crear nuestra cuenta en github.
- Descargar e instalar los paquetes necesarios.
- Crear nuestro repositorio o proyecto.
- Configurar y clonar nuestro proyecto a la pc.

Puedes adquirir una cuenta y configurarla desde el sitio web en [Github](https://github.com/)

Descargar los paquetes 

[git-1.8.4.2.pet](http://ubuntuone.com/7kqwljWMJN8Pg808cdIc0V)

[ccgit-0.1.pet](http://ubuntuone.com/5zjNYiDOCJVtI9hbpfdwxy)

Crear un repositorio. 
Donde alojar nuestro proyecto no es complicado, hasta ahora solo
nos hemos manejado desde el sitio web y descargado los paquetes que nos permitirán 
configurar y usar git en nuestro ordenador.

![screenshot](http://i.imgur.com/T5oZAQ3.png)

Una vez creado nuestro repositorio solo nos falta configurar nuestra cuenta en el 
ordenador, ahi es donde entra en accion el script de automatizacion ccgit, es recomendable
empezar un proyecto con un archivo Readme y con un archivo de Licencia para proyectos
libres.

Escribe en terminal 

`ccgit`

Originalmente el script fue escrito por D-coy y su finalidad es configurar git en 
nuestro ordenador con ciertos parámetros ya establecidos, veamos una breve descripción.

##Tu identidad 

- git config --global user.name woofshahenuzp donde "wooshahenzup" es tu usuario
- git config --global user.email tu-correo@bla.com "escribes tu correo"`

##Otros parámetros
 
- git config --global core.editor geany  Tu editor "geany" es por default
- git config --global core.pager '' 
- git config --global color.ui true
- git config --global http.sslVerify false
- git config --global push.default matching
- git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

Esto es lo que hace el script, si hay alguna configuración extra solo edita
el archivo en /usr/bin/ccgit 

Bien el script te pregunta si quieres clonar o bajar un repositorio a tu ordenador 
y que escribas la url para ello solo vas y copias al portapapeles (copy to clipboard ).

![screenshot](http://i.imgur.com/bVYez9m.png)

Copias la URL donde te lo indique el script, siempre puedes bajar cualquier repositorio
con el comando 

`git clone`

Seguido de la URL del repositorio ej:

`git clone https://github.com/Woofshahenzup/Puppyes-ccgit.git`

Ahora ya podemos ver nuestro proyecto en nuestra carpeta HOME, es en este punto que
podremos trabajar nuestro proyecto con tranquilidad. 

Demasiada teoria? bueno simplificando las cosas solo corriendo el script de automatizacion ya puedes
tener lo anteriormente explicado claro con los paquetes instalados y con tu cuenta creada.

##Trabajando en tu ordenador 

![screenshot](http://i.imgur.com/16yzwOn.png)

Bien ahora trabaja normal en tu directorio, dependiendo a las necesidades de tu proyecto
- Creando un documento 
- Creando una estructura de un paquete ejemplo /usr/bin/ccgit el archivo que he subido a este
  proyecto.
- Editando un documento, script o cualquier otra cosa
- Agregando mas archivos con diferentes extensiones .png .txt etc

Cada vez que trabajas dentro de tu directorio proyecto git esta guardando las modificaciones
esperando que que estas sean enviadas a tu repositorio remoto osea el que esta en el sitio web

##Comandos útiles

Haz un cambio, modifica algun archivo, sube uno nuevo lo que tu quieras, ahora revisa el estado

`git status`

![screenshot](http://i.imgur.com/0Pyw3nA.png)

En letras rojas esta el archivo que modifique, y ademas unos dialogos de ayuda 
- git add file para actualizar lo que se le va a hacer commit
- git checkout -- file para descartar algun archivo. 

Entonces hacemos el siguiente comando 

`git add .`

Asi registramos nuestros cambios ( añádidos al index ) veamos como cambia ahora si 
hacemos nuevamente `git status`.

![screenshot](http://i.imgur.com/EZvCJ3a.png)

Letras verdes indican que ya registraste los cambios, mas comandos de ayuda
- git reset HEAD file  para deshacerlos del index.

Muy bien ahora vamos a hacer el commit para incluirlos al HEAD 
recuerda esta es una guia practica si quieres saber mas puedes buscar tutoriales 
más explicados sobre la terminologia de git [( Guia rápida )](http://rogerdudler.github.io/git-guide/index.es.html)

Pero bueno hagamos el commit. 

`git commit -m "Mensaje del commit entre comillas"`

![screenshot](http://i.imgur.com/EZvCJ3a.png)

Como ven 1 archivo cambio, se insertaron 37, y se borraron 4

Ahora nuestros cambios ya pueden ser enviados al repositorio remoto si nosotros
queremos.

`git push`

![screenshot](http://i.imgur.com/9sU6Q0m.png)

En este punto se te preguntará tu usuario y contraseña de git para poder guardar
los cambios en tu repositorio remoto.
Puedes ver el registro de los cambios que has hecho en tu repositorio usando el 
comando.

`git lg`  (el cual es un alias a git log previamente configurado con el script de automatización) 

![screenshot](http://i.imgur.com/jyeAR89.png)

Hasta este punto ya hemos explicado lo mas básico de git en Puppy ahora ya puedes
gestionar tus versiones y proyectos de una forma rápida y sencilla.
Si haces esto de una forma repetitiva podras ver que es tan complicado como parece.


