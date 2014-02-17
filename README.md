Puppyes-ccgit
=============

Guía para mortales, configura y clona repositorios de git en PuppyLinux

La perspectiva de un usuario común y corriente sin poderes mutantes.
¿Pero cual es la idea de usar git para gestionar un proyecto ya sea personal o 
grupal?, bueno veamos algunas ventajas.

- Se puede trabajar en el proyecto incluso sin una conexión a internet
- Es mas rápido desarrollar proyectos.
- Se puede saber quien ha tocado qué y cuándo el código.
- Se puede volver atrás de forma rápìda.
- Puede controlar las versiones atavés de etiquetas.  
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
ordenador, ahi es donde entra en acción el script de automatización ccgit, es recomendable
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
y que escribas la URL para ello solo vas al sitio web de tu cuenta en github y 
copias al portapapeles (copy to clipboard ).

![screenshot](http://i.imgur.com/bVYez9m.png)

Copias la URL donde te lo indique el script, siempre puedes bajar cualquier repositorio
con el comando 

`git clone`

Seguido de la URL del repositorio ej:

`git clone https://github.com/Woofshahenzup/Puppyes-ccgit.git`

Ahora ya podemos ver nuestro proyecto en nuestra carpeta HOME, es en este punto que
podremos trabajar nuestro proyecto con tranquilidad. 

¿Demasiada teoria? bueno simplificando las cosas solo corriendo el script de automatizacion ya puedes
tener lo anteriormente explicado claro con los paquetes instalados y con tu cuenta creada.

##Trabajando en tu ordenador 

![screenshot](http://i.imgur.com/16yzwOn.png)

Bien ahora trabaja normal en tu directorio, dependiendo a las necesidades de tu proyecto
- Creando un documento 
- Creando una estructura de un paquete ejemplo /usr/bin/ccgit el archivo que he subido a este
  proyecto.
- Editando un documento, script o cualquier otra cosa
- Agregando mas archivos con diferentes extensiones .png .txt etc

Cada vez que trabajas dentro de tu directorio proyecto, git esta guardando las modificaciones
esperando que que éstas sean enviadas a tu repositorio remoto osea el que esta en el sitio web

##Comandos útiles

Haz un cambio, modifica algun archivo, sube uno nuevo lo que tu quieras, ahora revisa el estado

`git status`

![screenshot](http://i.imgur.com/0Pyw3nA.png)

En letras rojas esta el archivo que modifiqué, y además unos dialogos de ayuda 
- git add file para actualizar lo que se le va a hacer commit
- git checkout -- file para descartar algun archivo. 

Entonces hacemos el siguiente comando 

`git add .`

Asi registramos nuestros cambios ( añadidos al index ) veamos como cambia ahora si 
hacemos nuevamente `git status`.

![screenshot](http://i.imgur.com/EZvCJ3a.png)

Letras verdes indican que ya registraste los cambios, mas comandos de ayuda
- git reset HEAD file  para deshacerlos del index.

Muy bien ahora vamos a hacer el commit para incluirlos al HEAD 
recuerda esta es una guia practica si quieres saber mas puedes buscar tutoriales 
más explicados sobre la terminologia de git [( Guia rápida )](http://rogerdudler.github.io/git-guide/index.es.html)

Pero bueno hagamos el commit. 

`git commit -m "Mensaje del commit entre comillas"`

![screenshot](http://i.imgur.com/Xq8YqDQ.png)

Como ven 1 archivo cambió, se insertaron 37, y se borraron 4

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
Si practicas esto repetidaménte podras ver que no es tan complicado como parece.

## Creando ramas y su función

Una rama en git a manera fácil de entender es una division de nuestro proyecto principal
de hecho al proyecto en si se le conoce como rama "master" de ahi podemos partir ramificandolo 
y su finalidad puede variar de acuerdo a las necesidades aqui algunos ejemplos con este 
proyecto.

- Quiero agregar una nueva funcionabilidad al script de automatización, un parámetro 
  extra y no se si va a funcionar.
- El script tiene errores de ejecución y voy a hacer cambios mas radicales pero no quiero 
  perder la sintaxis del original
  
Entonces creo una rama paralela al proyecto y eso me servirá para trabajar cómodo sin 
cambiar mi trabajo en la rama 'master'.

`git checkout -b rama-prueba` 

He nombrado a la rama que voy a crear 'rama-prueba' 

![screenshot](http://i.imgur.com/zgzjbRQ.png)

El parámetro extra `-b` me traslada de una vez a la rama-prueba que he creado.
Para ver donde estoy parado puedo usar el comando 

`git branch`

![screenshot](http://i.imgur.com/azR7TbE.png)

ahora puedo trabajar en la rama haciendo mis pruebas, commits, push, etc. Como estoy editando 
este archivo Readme.md estos cambios solo se verán en mi 'rama-prueba' después vamos a fusionar los 
cambios a la rama master.

Si quiero que otros trabajen en la rama-prueba que yo he crado la tengo que subir a 
mi repositorio remoto 

`git push origin rama-prueba`

![screenshot](http://i.imgur.com/JNqlpr7.png)

Otros comandos útiles

- git checkout master  ( vuelve a la rama principal )
- git branch -d rama-prueba ( borra la rama prueba )

## Fusionando cambios

Bueno  me gustaron los cambios que hice en la rema-prueba ahora, volvemos a la rama 
principal del proyecto o rama master para hacer la fusión o para aplicar los cambios
a la rama master.

`git checkout master`

recuerda que siempre por si no estas seguro en que rama estas, puedes usar `git branch`.
Bien ahora fusionamos nuestra rama-prueba.
Debes aseguarte que tanto las ramas master y pruebas o como las renombres deben estar 
actualizados sus cambios, siempre es bueno ver el estado de las ramas y hacer los 
respectivos commits y push para actualizar los cambios antes de fusionar ramas.

`git merge rama-master`

Y borramos la rama-prueba y la quitamos de nuestro repositorio local y remoto ya que no
la vamos a necesitar màs por el momento.

`git branch -d rama-prueba` Borra la rama de nuestro repositorio local.

![screenshot](http://i.imgur.com/d2Y70rj.png)

`git push origin :rama-prueba` Elimina la rama de nuestro repositorio remoto.

![screenshot](http://i.imgur.com/zyWWSsE.png)






