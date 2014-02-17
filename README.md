Puppyes-ccgit
=============

Guia para mortales, configura y clona repositorios de git en PuppyLinux

La perspectiva de un usuario comun y corriente sin poderes mutantes, pero
cual es la idea de usar git para gestionar un proyecto ya sea personal o 
grupal, bueno veamos algunas ventajas.

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
ordenador, ahi es donde entra en accion el script de automatizacion ccgit 

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


