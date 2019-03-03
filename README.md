# EJERCICIO

1. Proponer una arquitectura de bolsillo para un gestor documental.
2. Justificar la selección de la arquitectura.

# INTEGRANTES

* Carmen Aldana
* Andres Felipe Martinez
* Juan Carlos Cruz

# GESTOR DOCUMENTAL

Para hacer una identificación arquitectural guiada y certera, se identifica los requisitos mínimos para un sistema de este tipo.

* Requisitos de usuario:

1.	Se necesita de una solución tecnológica que permita la carga, actualización, descarga y eliminación de diferentes tipos de archivo tales como: Pdf, texto, gráficos, etc.
2.	La solución deberá soportar el acceso de más de 1000 usuarios que ejecutarán las diferentes acciones sobre los archivos.
3.	Así mismo, la solución propuesta deberá salvaguardar la seguridad de la información en todas sus características.
4.	La solución propuesta deberá presentar interfaces de usuario que sean amigables y de fácil uso.
5.	El sistema deberá estar disponible 7x24 los 365 días del año.
6.	Además, deberá ser fiable y confiable en su operación.

* Requisitos de sistema:

1.1 El sistema deberá permitir la carga de diferentes tipos de archivos almacenándolos en un repositorio de archivos con suficiente capacidad para soportar la operación del número de usuarios estimados para el sistema.
1.2 Se estima que el número de usuarios del sistema será de 1000 y que cada usuario podrá usar una capacidad de 10 GB.
1.3 Los tipos de archivos que serán almacenados en el repositorio son: TXT, DOCX, XLS, PDF, JPG, BMP, entre otros. No se permitirá el almacenamiento de archivos ejecutables.
1.4 El sistema permitirá la modificación de los archivos cargados en el repositorio mediante interfaz provista por el mismo sistema.
1.5 También se deberá permitir la descarga y eliminación de los archivos que previamente han sido cargados.
1.6 El sistema deberá almacenar toda la información relacionada con las operaciones que hagan los usuarios sobre el sistema.
1.7 Debido a que el sistema deberá asociar las operaciones realizadas con los usuarios que soporta, se deberán proporcionar todas las funciones que permitan la administración de los usuarios y sus perfiles.
2.1 El sistema deberá soportar 1.000 usuarios en total y 100 de ellos de manera concurrente.
3.1 El sistema deberá soportar las características de seguridad definidas en la norma ISO25010: confidencialidad, integridad, no repudio, autenticidad y responsabilidad.
3.2 Las características de confidencialidad, autenticidad e integridad se resolverán implementando mecanismos de autorización, autenticación y de cifrado de las comunicaciones mediante el uso de certificados digitales.
3.3 Las características de no repudio y responsabilidad se resolverán mediante la implementación de registros para auditoría de cada una de las operaciones realizadas por el usuario en el sistema.
4.1 El sistema deberá tener en cuenta la guía de usabilidad vigente de MINTIC para su implementación.
5.1 El sistema deberá estar soportado por una infraestructura redundante y escalable alojado en centro de datos certificado como mínimo en nivel 3.
6.1 El sistema deberá soportar las características de fiabilidad definidas en la norma ISO25010 y en particular: tolerancia a fallos y capacidad de recuperación.
6.2 La característica de capacidad de recuperación será implementada mediante el registro de LOGS de monitoreo en donde se registre el estado del sistema cada vez que se realiza una operación.
6.3 La capacidad de recuperación se implementará mediante la lectura de LOGS de monitoreo y la restauración del sistema al estado estable anterior al fallo.

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
