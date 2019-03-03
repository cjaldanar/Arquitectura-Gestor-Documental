# EJERCICIO

1. Proponer una arquitectura de bolsillo para un gestor documental.
2. Justificar la selección de la arquitectura.

# INTEGRANTES

* Carmen Aldana
* Andres Felipe Martinez
* Juan Carlos Cruz

# GESTOR DOCUMENTAL

Para hacer una identificación arquitectural guiada y certera, se identifica los requisitos mínimos para un sistema de este tipo.

# * Requisitos de usuario:

1.	Se necesita de una solución tecnológica que permita la carga, actualización, descarga y eliminación de diferentes tipos de archivo tales como: Pdf, texto, gráficos, etc.
2.	La solución deberá soportar el acceso de más de 1000 usuarios que ejecutarán las diferentes acciones sobre los archivos.
3.	Así mismo, la solución propuesta deberá salvaguardar la seguridad de la información en todas sus características.
4.	La solución propuesta deberá presentar interfaces de usuario que sean amigables y de fácil uso.
5.	El sistema deberá estar disponible 7x24 los 365 días del año.
6.	Además, deberá ser fiable y confiable en su operación.

# * Requisitos de sistema:

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


   # ARQUITECTURA PROPUESTA:

A partir de los requisitos identificados, se identifica la siguiente arquitectura de la solución desde un punto de vista lógico:

![Imagen arquitectura](https://github.com/cjaldanar/Arquitectura-Gestor-Documental/blob/master/Arquitectura%20Gestor%20Documental.png)

Se establece una arquitectura cliente – servidor de tres capas con los siguientes elementos:
* Contenedor Web en donde se implementarán las capas de presentación y aplicación. Además, soportará parte o toda la implementación de los requisitos identificados para el sistema.
* Repositorio de archivos en donde se implementará una parte de la capa de servidores que será complementada por la base de datos. De manera particular, esta capa soportará la implementación total o parcial de los siguientes requisitos: 1.1, 1.2, 1.5, 2.1, 3.2, 5.1, 6.1, 6.2, 6.3.
* Base de datos archivos en donde se implementará una parte de la capa de servidores que será complementada por el repositorio de archivos. De manera particular, esta capa soportará la implementación total o parcial de los siguientes requisitos: 1.6, 1,7, 2.1, 3.2, 3.3, 5.1, 6.1, 6.2, 6.3.

# JUSTIFICACIÓN

* La arquitectura de solución propuesta realiza todos y cada uno de los requisitos identificados para el sistema y permitirá una implementación tecnológica con herramientas e infraestructura de software vigentes y propuestas dentro de los marcos de trabajo más usados como JEE. 
* La solución propuesta es confiable y escalable tanto horizontal como verticalmente lo asegurará su madurez y robustez.
* Permitirá el uso de estándares y marcos de trabajo vigentes para la implementación de los diferentes artefactos de software que se definan para el sistema de información a implementar. Sin embargo, tiene un punto débil y es que no ofrece las funcionalidades a través de servicios sino a través de una aplicación lo cual restringirá el número y variedad de dispositivos desde los cuales podrá ser usada. 
