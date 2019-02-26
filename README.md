# Arquitectura-Gestor-Documental
Proponer una arquitectura de bolsillo para un gestor documental
INTEGRANTS
Carmen  Aldana 
Andres Felipe Martinez
Juan Carlos Cruz
![Imagen arquitectura](https://github.com/cjaldanar/Arquitectura-Gestor-Documental/blob/master/Arquitectura%20Gestor%20Documental.png)


Justificación:
Decidimos hacer una aplicación orientada a la web, porque en el negocio donde nos centramos la mayoría de aplicacionesse están migrando a esto para tener un unico portal de aplicaciones para el usuario final, por la ventaja de ser multiplataforma y la administración de esta.

Esogimos una BD SQLServer, porque la cantidad de comunicados de operaciones, reembolsos y "la otra no me acuerdo", no es muy siginificante, allí tendremos solo los apuntadores o referencias a los archivos, es decir que no se almacenarán los archivos en esta.

Se dejó unserviodr de archivos y su cu opia, as cualtes estarán conectadas es el aservidor EWeb qu etraerá la referencia de los archivos desde la BD y buscará el archivo en este. Lo anterior con el finque si crecen muchos archivos es más fácil expandir estos servidores, que agrandar la BD(En caos que los archivos se hubieran guraddo allí).


cmoentarios: CARMEN creo que donde dice Angular JS, es mejor dejar Frontend a manera genral, estamos mexclando arquitectura de alto nivel con Tecnogloías, en caso de ser así, deberíamos colocar entonces las tecnologías dle servidor web y los servideores de archivos.
