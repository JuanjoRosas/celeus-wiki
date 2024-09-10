<!-- TOC start (generated with https://github.com/derlin/bitdowntoc) -->

- [Reglas de negocio](#reglas-de-negocio)
   * [Proyecto de construcción](#proyecto-de-construcción)
      + [Propiedades](#propiedades)
         - [Nombre:](#nombre)
         - [Lista de espacios físicos:](#lista-de-espacios-físicos)
   * [Espacio físico](#espacio-físico)
      + [Subcategorias](#subcategorias)
         - [Espacio físico simple](#espacio-físico-simple)
            * [Propiedades](#propiedades-1)
               + [Código:](#código)
            * [Transacciones](#transacciones)
               + [inserción a espacio compuesto](#inserción-a-espacio-compuesto)
               + [remoción de espacio compuesto](#remoción-de-espacio-compuesto)
         - [Espacio físico compuesto](#espacio-físico-compuesto)
            * [Propiedades](#propiedades-2)
               + [lista de espacios simples:](#lista-de-espacios-simples)
      + [Propiedades de la categoría madre](#propiedades-de-la-categoría-madre)
         - [Medidas físicas:](#medidas-físicas)
         - [Tipo de espacio:](#tipo-de-espacio)
         - [Valor base:](#valor-base)
         - [Valorización:](#valorización)
      + [Transacciones](#transacciones-1)
         - [Asignación de precio base](#asignación-de-precio-base)
         - [Asignación de valorización](#asignación-de-valorización)
   * [Tipo de espacio](#tipo-de-espacio-1)
      + [Propiedades](#propiedades-3)
         - [Margen de ganancia:](#margen-de-ganancia)
      + [Transacciones](#transacciones-2)
         - [Asignacion de margen de ganancia](#asignacion-de-margen-de-ganancia)
   * [Complemento](#complemento)
      + [Propiedades](#propiedades-4)
         - [Tipo de complemento:](#tipo-de-complemento)
   * [Tipo de complemento](#tipo-de-complemento-1)
      + [Propiedades](#propiedades-5)
         - [Nombre:](#nombre-1)
         - [Descripción:](#descripción)
         - [Categoria:](#categoria)
         - [Lista de tipos de espacio:](#lista-de-tipos-de-espacio)
         - [Lista de procedimientos:](#lista-de-procedimientos)
      + [Transacciones](#transacciones-3)
         - [Liberación para tipo de espacio](#liberación-para-tipo-de-espacio)
         - [Retiro para tipo de espacio](#retiro-para-tipo-de-espacio)
         - [Inserción de procedimiento](#inserción-de-procedimiento)
         - [Remoción de procedimiento](#remoción-de-procedimiento)
   * [Procedimiento](#procedimiento)
      + [Propiedades](#propiedades-6)
         - [Nombre:](#nombre-2)

<!-- TOC end -->


<!-- TOC --><a name="reglas-de-negocio"></a>
# Reglas de negocio
Esta es la documentación de las reglas de negocio de la compañía Celeus Group relevantes para la ejecución de los proyectos tecnológicos de la compañía.
<!-- TOC --><a name="proyecto-de-construcción"></a>
## Proyecto de construcción
Se entiende como proyecto a una propuesta de construcción cuya responsabilidad de ejecución total o parcial fue adquirida por la compañía y/o sus figuras legales.
<!-- TOC --><a name="propiedades"></a>
### Propiedades
Cada proyecto tiene ciertas propiedades relevantes para el negocio.
<!-- TOC --><a name="nombre"></a>
#### Nombre:
Cada proyecto tiene un nombre por el cual se puede referir a él.
<!-- TOC --><a name="lista-de-espacios-físicos"></a>
#### Lista de espacios físicos:
Es la lista de [espacios físicos](#espacio-físico) que contiene el proyecto de construcción.
<!-- TOC --><a name="espacio-físico"></a>
## Espacio físico
Se entiende como espacio físico a volúmenes espaciales continuos cuyas fronteras se determinan con posiciones relativas a otra posición de referencia que hace parte del [proyecto de construcción](#proyecto-de-construcción) al cual pertenece el espacio.
<!-- TOC --><a name="subcategorias"></a>
### Subcategorias
Un espacio físico se puede clasificar de dos formas distintas:
<!-- TOC --><a name="espacio-físico-simple"></a>
#### Espacio físico simple
Esta clasificación hace referencia a un espacio físico cuyo volumen no contiene ni colisiona con algún otro volumen de otro espacio físico.
<!-- TOC --><a name="propiedades-1"></a>
##### Propiedades
El espacio físico simple tiene las siguientes propiedades relevantes para el negocio
<!-- TOC --><a name="código"></a>
######  Código:
El código es una propiedad arbitraria que se utiliza para diferenciar al espacio físico simple de cualquier otro.
<!-- TOC --><a name="transacciones"></a>
##### Transacciones
Sobre cada espacio simple se pueden realizar las siguientes transacciones relevantes para el negocio
<!-- TOC --><a name="inserción-a-espacio-compuesto"></a>
###### inserción a espacio compuesto
La inserción del espacio simple a un [espacio compuesto](#espacio-físico-compuesto) consiste en la agregación del espacio simple a la [lista de espacios simples](#lista-de-espacios-simples) que son contenidos por el espacio compuesto. Para poder realizar una inserción se deben cumplir las siguientes reglas:
1. Entre la fecha de inserción de un determinado espacio simple a una lista y la fecha de inserción anterior más cercana del mismo espacio simple a la misma u otra lista debe existir una [fecha de remoción](#remoción-de-espacio-compuesto) de dicho espacio simple de la misma lista a la que fue añadido con anterioridad. En otras palabras, no se puede agregar un espacio simple a cualquier lista si este todavía se encuentra añadido a alguna lista.
2. Congruencia espacial y estabilidad estructural. Estás son reglas relacionadas con implicaciones físicas de unir varios [espacios](#espacio-físico-simple). En esta documentación no se entra en detalle pues no son necesarias para los desarrollos pendientes.
<!-- TOC --><a name="remoción-de-espacio-compuesto"></a>
###### remoción de espacio compuesto
La remoción del espacio simple de un espacio compuesto consiste en la eliminación del espacio simple de la lista de espacios simples que son contenidos por el espacio compuesto. Para poder realizar una remoción se deben cumplir las siguientes reglas:
1. Entre la fecha de remoción de un determinado espacio simple de una lista y la fecha de remoción anterior más cercana del mismo espacio simple de la misma u otra lista debe existir una fecha de inserción de dicho espacio simple a la misma lista de la que desea remover el espacio en cuestión. En otras palabras, no se puede eliminar un espacio simple de una lista si este todavía no se ha añadido a dicha lista.
<!-- TOC --><a name="espacio-físico-compuesto"></a>
#### Espacio físico compuesto
El espacio físico compuesto hace referencia a un espacio físico cuyo volumén envuelve por completo a los volumenes de los [espacios físicos simples](#espacio-físico-simple) que lo conforman. Es decir, un espacio físico se compone de espacios físicos simples más pequeños a los cuales contiene. Un ejemplo es un penthouse que es un espacio físico compuesto por dos espacios simples (apartamentos).
<!-- TOC --><a name="propiedades-2"></a>
##### Propiedades
El espacio físico compuesto tiene las siguientes propiedades relevantes para el negocio
<!-- TOC --><a name="lista-de-espacios-simples"></a>
###### lista de espacios simples:
Es la lista de los espacios simples a los que contiene el espacio compuesto. Cada lista es única para cada espacio compuesto. Es decir, la lista de espacios simples se utiliza para diferenciar al espacio compuesto de cualquier otro espacio comupuesto.
<!-- TOC --><a name="propiedades-de-la-categoría-madre"></a>
### Propiedades de la categoría madre
 Cada [espacio físico](#espacio-físico) tiene ciertas propiedades relevantes para el negocio y que son comunes o compartidas entre los espacios físicos simples y los compuestos.
<!-- TOC --><a name="medidas-físicas"></a>
#### Medidas físicas:
Esta propiedad engloba todas las medidas espaciales que definen el volumen del espacio físico. En esta documentación no se entra en detalle para cada una debido a que no es necesario para los desarrollos pendientes.
<!-- TOC --><a name="tipo-de-espacio"></a>
#### Tipo de espacio:
Esta propiedad hace referencia a el proposito previsto para el espacio. Un ejemplo es un espacio que se construyo con el proposito de ser habitable, en dicho caso su [tipo](#tipo-de-espacio-1) sería "Apartamento".
<!-- TOC --><a name="valor-base"></a>
#### Valor base:
Este valor hace referencia a la representación cuantivativa en moneda local del valor intrinseco del espacio físico dentro de un periodo de tiempo.
<!-- TOC --><a name="valorización"></a>
#### Valorización:
Es la representación cuantitativa en moneda del valor añadido o sustraido que tiene el espacio físico debido a condiciones del mercado para un periodo de tiempo.
<!-- TOC --><a name="transacciones-1"></a>
### Transacciones
Sobre cada espacio se pueden hacer las siguientes transacciones
<!-- TOC --><a name="asignación-de-precio-base"></a>
#### Asignación de precio base
Este proceso hace referencia a la asignación de un [valor base](#valor-base) que entra en rigor desde la fecha en la que se hace la asignación hasta la siguiente fecha de asignación más cercana o en su defecto hasta la fecha presente.
<!-- TOC --><a name="asignación-de-valorización"></a>
#### Asignación de valorización
Este proceso hace referencia a la asignación de una [valorización](#valorización) que entra en rigor desde la fecha en la que se hace la asignación hasta la siguiente fecha de asignación más cercana o en su defecto hasta la fecha presente.
<!-- TOC --><a name="tipo-de-espacio-1"></a>
## Tipo de espacio
Como se mencionó anteriormente, el tipo de espacio hace referencia al uso previsto que se pensó para el espacio.
<!-- TOC --><a name="propiedades-3"></a>
### Propiedades
Cada tipo de espacio tiene las siguientes propiedades relevantes para el negocio
<!-- TOC --><a name="margen-de-ganancia"></a>
#### Margen de ganancia:
El margen de ganancia para un tipo de espacio es el valor en moneda local que se espera recibir por encima del [valor base](#valor-base) más la [valorización](#valorización) del espacio fisico. Esto implica que se espera que el margen de ganancia no sea menor a cero.
<!-- TOC --><a name="transacciones-2"></a>
### Transacciones
Sobre cada tipo de espacio se pueden hacer las siguientes transacciones.
<!-- TOC --><a name="asignacion-de-margen-de-ganancia"></a>
#### Asignacion de margen de ganancia
Este proceso hace referencia a la asignación de un [margen de ganancia](#margen-de-ganancia) que entra en rigor desde la fecha en la que se hace la asignación hasta la siguiente fecha de asignación más cercana o hasta la fecha presente en su defecto.
<!-- TOC --><a name="complemento"></a>
## Complemento
Un complemento es un objeto o conjuntos de objetos que pueden instalarse físicamente en un o unos determinados [tipos de espacio](#tipo-de-espacio-1) para complementar el uso previsto del espacio.
<!-- TOC --><a name="propiedades-4"></a>
### Propiedades
Cada Complemento tiene una serie de propiedades relevantes para el negocio.
<!-- TOC --><a name="tipo-de-complemento"></a>
#### Tipo de complemento:
El tipo de complemento hace referencia a la labor que desempeña  el complemento en el espacio en el que se instala.
<!-- TOC --><a name="tipo-de-complemento-1"></a>
## Tipo de complemento
Como se mencionó anteriormente, un tipo de complemento se entiende como la labor que desempeña el complemento al instalarse a en cualquier espacio físico.
<!-- TOC --><a name="propiedades-5"></a>
### Propiedades
Cada tipo de complemento tiene las siguientes propiedades relevantes para el negocio.
<!-- TOC --><a name="nombre-1"></a>
#### Nombre:
Es el nombre descriptivo del tipo de complemento, y que se utiliza para diferenciarlo de cualquier otro tipo de complemento.
<!-- TOC --><a name="descripción"></a>
#### Descripción:
Es una descripcción detallada del procedimiento de instalación y de los elementos instalados en el tipo de complemento.
<!-- TOC --><a name="categoria"></a>
#### Categoria:
Es la clasificación dentro de la que entra el tipo de complemento según la labor que desempeña. La categoría puede ser la misma para varios tipos de elementos. Un ejemplo es la categoría "Kit de acabado" que engloba tanto los tipos de complemento "Kit de acabado de suelo" como "Kit de cocina closet".
<!-- TOC --><a name="lista-de-tipos-de-espacio"></a>
#### Lista de tipos de espacio:
Es la lista de los [tipos de espacio](#tipo-de-espacio-1) al los cuales se les puede instalar el tipo de complemento.
<!-- TOC --><a name="lista-de-procedimientos"></a>
#### Lista de procedimientos:
Cada tipo de complemento tiene una lista de [procedimientos](#procedimiento) en orden consecutivo que se realizan durante la instalación del complemento. Esta lista ayuda a saber que tipos de complementos coinciden en algún o algunos procedimientos. Un ejemplo hipotético serían dos tipos de complementos que tengan dentro de su lista el procedimiento de "instalación de suelo". Cada procedimiento de la lista tiene un ordén de ejecución y una duración en tiempo.
<!-- TOC --><a name="transacciones-3"></a>
### Transacciones
Sobre cada tipo de complemento se pueden realizar las siguientes transacciones relevantes para el negocio.
<!-- TOC --><a name="liberación-para-tipo-de-espacio"></a>
#### Liberación para tipo de espacio
Liberar un tipo de complemento para un [tipo de espacio](#tipo-de-espacio-1) consiste en la agregación de dicho tipo de espacio a la [lista de tipos de espacio](#lista-de-tipos-de-espacio) del complemento. Para poder realizar una liberación deben cumplirse las siguientes reglas:
1. Entre la fecha de liberación de un determinado tipo de complemento para un determinado tipo de espacio y la fecha de liberación anterior más cercana del mismo tipo de complemento para el mismo tipo de espacio debe existir una fecha de retiro de dicho tipo de complemento para el mismo tipo de espacio. En otras palabras, no puede liberarse un tipo de complemento para un tipo de espacio si previamente se hizo exactamente la misma liberación y sigue activa.
<!-- TOC --><a name="retiro-para-tipo-de-espacio"></a>
#### Retiro para tipo de espacio
Retirar un tipo de complemento para un tipo de espacio consiste en la eliminación del tipo de espacio de la [lista de tipos de espacio](#lista-de-tipos-de-espacio) del tipo de complemento. Para poder realizar un retiro deben cumplirse las siguientes reglas:
1. Entre la fecha de retiro de un determinado tipo de complemento para un determinado tipo de espacio y la fecha de retiro anterior más cercana del mismo tipo de complemento para el mismo tipo de espacio debe existir una fecha de liberación del dicho tipo de complemento para el mismo tipo de espacio. En otras palabras, no puede retirarse un tipo de complemento para un tipo de espacio si previamente se hizo exactamente el mismo retiro y sigue activo.
<!-- TOC --><a name="inserción-de-procedimiento"></a>
#### Inserción de procedimiento
Es la inserción de un [procedimiento](#procedimiento) dentro la [lista de procedimientos](#lista-de-procedimientos) del tipo de complemento. La inserción debe tener tanto el procedimien como la fecha en la que se inserta, la duración del procedimiento y la posición consecutiva en la que se inserta. Para poder realizar una inserción de un procedimiento dentro de la lista deben cumplirse las siguientes reglas:
1. Entre la fecha de inserción de un determinado procedimiento en una determinada posición dentro de una lista y la fecha de inserción anterior más cercana del mismo procedimiento a la misma lista y en la misma posición debe existir una fecha de remoción de dicho procedimiento de la misma lista y en la misma posición. En otras palabras, no se puede insertar un procedimiento a una lista en una posición si este ya fue agregado en la misma posición y sigue presente en la lista.
<!-- TOC --><a name="remoción-de-procedimiento"></a>
#### Remoción de procedimiento
Es la eliminación de un procedimiento de la lista de procedimientos del tipo de complemento. La eliminación debe tener tanto el procedimien como la fecha en la que se elimina y la posición consecutiva de la que se elimina. Para poder realizar una eliminación de un procedimiento de de la lista deben cumplirse las siguientes reglas:
1. Entre la fecha de eliminación de un determinado procedimiento en una determinada posición en una lista y la fecha de eliminación anterior más cercana del mismo procedimiento a la misma lista y en la misma posición debe existir una fecha de inserción de dicho procedimiento en la misma lista y en la misma posición. En otras palabras, no se puede eliminar un procedimiento de una lista en una posición si este no ha sido agregado antes en la misma posición en la lista.

<!-- TOC --><a name="procedimiento"></a>
## Procedimiento
Se entiende como procedimiento a una tarea que se lleva a cabo durante la instalación de un [complemento](#complemento).
<!-- TOC --><a name="propiedades-6"></a>
### Propiedades
Cada procedimiento tiene una serie de propiedades relevantes para el negocio.
<!-- TOC --><a name="nombre-2"></a>
#### Nombre:
Es el nombre que describe al procedimiento y que lo sirve para diferenciarlo de cualquier otro procedimiento.