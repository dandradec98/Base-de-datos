#Repaso de Base de datos

##ACID

* Atomicidad: cada operación se ejecuta secuencialmente. O se ejecuta todo, o nada.
* Consistencia: la integridad de la BBDD no se puede romper mediante una operación. Solo se empieza aquello que se puede acabar.
* Aislamiento: una operación independiente no afecta a otras.
* Durabilidad: toda operación queda registrada y no se puede deshacer.

##PostgreSQL

Es un SGBD relacional, orientado a objetos y con fuerte soporte a operaciones ACID(Atomicidad, Consistencia, Aislamiento, y Durabilidad).

PostgreSQL introdujo conceptos del modelo objeto-relacional. 

###1. Características:

* Consultas complejas
* Llaves foráneas
* Triggers
* Vistas
* Integridad transaccional

##Sistemas de base de datos:

El término Sistema de Base de Datos se refiere a organizar componentes para almacenar, administra y usar datos dentro de un ambiente de base de datos. Consta de 5 partes:

###1. Hardware

Son los equipos físicos del sistema: PC, terminales, servidores, etc.

###2. Software

* El SO, el DBMS, y programas de utilería.

###3. Personas

* Los administradores del sistema
* Los administradores de la BD
* Los diseñadores de la BD
* Los analistas y programadores del sistema
* Los usuarios finales

###5. Procedimientos

Son las instrucciones y reglas que gobiernan el diseño y uso del sistema de base de datos. Los procedimientos hacen cumplir las normas por medio de las cuales se realizan los negocios dentro de la organizacion con sus clientes.

###6. Datos

Comprende el conjunto de datos almacenados en la base de datos.

##Arquitectura de Base de datos:

Los datos en los SGBD se describen en tres niveles de abstracción: Conceptual, Físico y Externo.

Los lenguajes de definición de datos o DDL, se emplean para definir los esquemas externo y conceptual.

En general para la filosofía de la estructura de base de datos que propone el modelo ANSI/SPARC que se estudiará a continuación.

####Arquitectura ANSI/SPARC

Posee 3 niveles:

1. Nivel de visión o externo(Vistas parciales de la BD)
2. Nivel Conceptual/lógico(Vista global de la BD)
3. Nivel físico(almacenamiento de la BD) 

###I. Esquema Conceptual

También conocido como esquema lógico. Describe los datos almacenados en tñerminos del modelo de datos del SGBD. En un SGBD relacional el esquema conceptual describe todas las relaciones almacenadas en la BD.

Ejemplo:

`Alumnos(ide: String, nombre: String)`

###II. Esquema físico

Especifica los detalles adicionales del almacenamiento. Resume el modo en que las relaciones se guardan en dispositivos de almacenamiento secundario como discos y cintas.

###III. Esquema externo

Permite personalizar el acceso a los datos de los usuarios y grupos de ellos.

###Independencia de datos

####I. Independencia de datos lógica

Se refiere a la inmunidad del modelo externo respecto a cambios en el modelo lógico como agregar nuevos tipos de datos, nuevos items o relaciones.

####II. Independencia de datos física.

Se refiere a la inmunidad del modelo lógico respecto a cambios en el modelo físico o interno

##Modelo Entidad-Relación

###Entidad:

Es un conjunto de objetos del mundo real sobre los cuales se desea mantener información. Representable a través de un rectángulo.

Posee propiedades, también llamados atributos.

###Atributo:

Es un dato que está asociado a cada ocurrencia de una entidad:

Ejemplo:

Sea le entidad empleado, puede contener los siguientes atributos:

* Nombre
* Dirección
* Salario

###Relaciones:

Es un asociación entre entidades, se representa mediante un rombo.

####Cardinalidad de relaciones:

Existen 2:

#####1. Máxima

######Relación uno a uno - 1:1
 
Una ocurrencia de A está asociado como máximo a una ocurrencia de B, y una ocurrencia en B está asocidad a no más de una ocurrencia en A.

![Relación uno a uno](http://3.bp.blogspot.com/_mCvQEc62fkA/S89Kpqh3lVI/AAAAAAAAABc/7cnTnunoBsM/s320/1a2.GIF)

######Relación uno a muchos - 1:N

Una ocurrencia de A está asocidad a varias ocurrencias de B, pero una ocurrencia de B debe estar asocuada como máximo a una ocurrencia en A.

![Relación uno a N](http://www.aulapc.es/usuarios/imalami/acces/80im)

######Relación de muchos a muchos - N:N

Una ocurrencia de A está asociada a cualquier número de ocurrencias de B y una ocurrencia en B está asociada a cualquier número de ocurrencias de B

![Relación de muchos a muchos](http://formacion.intef.es/pluginfile.php/37671/mod_imscp/content/1/Relaciones13_PEQUE.JPG)

#####2. Mínima

Al igual que en el caso anterior con la diferencia de que esta hace referencia a un mínmo de ocurrencias de una entidad A con relación a otra entidad B.

##Algebra Relacional

###Operadores sobre conjuntos

- Unión
- Intersección
- Diferencia
- Producto cartesiano

###Operadores específicos del álgebra relacional

- Selección
- Proyección
- Join
- División
- Renombramiento

###1. Selección

![Select](https://slideplayer.com/slide/3253766/11/images/65/Relational+Algebra+%28RA%29.jpg)


####2. Proyección

![Projection](https://slideplayer.com/slide/3253766/11/images/15/Relational+Algebra+%28RA%29.jpg)

###3. Intersección

![Intersection](https://image.slidesharecdn.com/techtudpptformat4-170425135619/95/intersection-operation-in-relational-algebra-4-638.jpg?cb=1493128683)

###4. Unión

![Union](https://3.bp.blogspot.com/-BBdUfXL5a_E/WSxAxePKTOI/AAAAAAAAFIY/5vvNj0J9zTYD2AefSpNnb0Z7k4M9-x14ACLcB/s1600/Relational%2BAlgebra%2B06.png)

###5. Diferencia

![Diference](https://3.bp.blogspot.com/-1vQFrPPjV4M/WSxA1UDcGSI/AAAAAAAAFIc/WZWAX5FXA4YU8-TzUuR7MlZWU4k1nMDVwCLcB/s1600/Relational%2BAlgebra%2B07.png)

###6. Producto cartesiano

![Cartesian product](https://4.bp.blogspot.com/-NubHSJYruEc/WSxAtiatR_I/AAAAAAAAFIU/3Hd707K98OIaYVepCMKVJZBZleU6_WqCACLcB/s640/Relational%2BAlgebra%2B05.png)

###7. Theta Join

![Theta Join](https://2.bp.blogspot.com/-Yu6v_Uo_eIA/WUYU0QaIesI/AAAAAAAAFMg/AYSDTdWhbZwviKKTknkj13gQrXl0Adv4gCLcBGAs/s640/Relational%2BAlgebra%2B-%2BJoin%2B01.png)

###8. Equi Join

![Equi Join](https://4.bp.blogspot.com/-pt_IKWsRkc0/WUYWNcEhkSI/AAAAAAAAFMs/3QwB2lYNNzIQPg0fPrVvZN-ky8o6YaiMACLcBGAs/s640/Relational%2BAlgebra%2B-%2BJoin%2B02.png)

###9. Natual Join
![Natural Join](https://1.bp.blogspot.com/-0O6O7-kulME/WUYX6WY3dDI/AAAAAAAAFM8/eF2JDVom1jAUuauYKDKIZicQgjuErH7VACLcBGAs/s640/Relational%2BAlgebra%2B-%2BJoin%2B04.png)

###10. Outer Join

![Outer Join](https://2.bp.blogspot.com/-GIl-ukVdkaI/WUYZ1EEXE4I/AAAAAAAAFNI/KCWdWt-34LU83x7PkylhHyG_YWpdXfwXACLcBGAs/s640/Relational%2BAlgebra%2B-%2BJoin%2B05.png)

###11. Semi Join

![Semi Join](https://4.bp.blogspot.com/-xj9dbPMj6ys/WUYieWrB1GI/AAAAAAAAFNY/DsYJMui_qYIuPBm5X-1IsVZJf0VrWTSygCLcBGAs/s640/Relational%2BAlgebra%2B-%2BJoin%2B06.png)

###12. Division

![Division](https://3.bp.blogspot.com/-bw4LVmTmSy8/WSxId2uT1mI/AAAAAAAAFIw/WIcjdWPmQV4HxylwR3aZlro_VPLz32U3QCLcB/s640/Relational%2BAlgebra%2B09.png)


