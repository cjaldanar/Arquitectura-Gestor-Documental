# EJERCICIO

1. Proponer una arquitectura de bolsillo para un gestor documental.
2. Justificar la selección de la arquitectura.

# INTEGRANTES

*Carmen  Aldana
*Andres Felipe Martinez
*Juan Carlos Cruz

# GESTOR DOCUMENTAL

   # ARQUITECTURA PROPUESTA CLIENTE/SERVIDOR:

![Imagen arquitectura](https://github.com/cjaldanar/Arquitectura-Gestor-Documental/blob/master/Arquitectura%20Gestor%20Documental.png)

# JUSTIFICACIÓN

Decidimos hacer una aplicación orientada a la web, porque en el negocio donde nos centramos la mayoría de aplicacionesse están migrando a esto para tener un unico portal de aplicaciones para el usuario final, por la ventaja de ser multiplataforma y la administración de esta.

Esogimos una BD SQLServer, porque la cantidad de comunicados de operaciones, reembolsos y "la otra no me acuerdo", no es muy siginificante, allí tendremos solo los apuntadores o referencias a los archivos, es decir que no se almacenarán los archivos en esta.

Se dejó unserviodr de archivos y su cu opia, as cualtes estarán conectadas es el aservidor EWeb qu etraerá la referencia de los archivos desde la BD y buscará el archivo en este. Lo anterior con el finque si crecen muchos archivos es más fácil expandir estos servidores, que agrandar la BD(En caos que los archivos se hubieran guraddo allí).


COMENTARIOS: CARMEN y JUAN creo que donde dice Angular JS, podríamos dejarlo de 2 opciones. Dejar "Frontend" a manera general en vez de AngularJS(estamos nombrando es la Tecnogloía), La otra forma es colocar las tecnologías en el resto de componentes, por decir en el servidor web y los servideores de archivos.Ejemplo: 
FRONT END:AngularJS,VueJS, ReactJS. 
SERVIDOR WEB: APACHE o NGINX.
SERVIDOR DE ARCHIVOS: Windows o Linux (De esto no estoy seguro).
BASE DE DATOS: SQLServer o PostegreSQL.
Exponiendo que nombramos las posiobles tecnologías, pero sería necesario tener un levantamiento de información más detallado para definir exctamente cuál.Por otro lado también Sería Bueno nombrar exactamente qué hace el negocio en que nos centramos, una introducción praqueentrar al lector en contexto de porque  construimos esta arquitectura.
