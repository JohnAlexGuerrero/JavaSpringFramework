@RequestMapping("/") se para por parametro el valor, que es la URI que debe mapearse con este metodo
parametros que puede recibir @RequestMapping:

- name: el nombre del mapeo
- method: peticion HTTP GET, POST, PUT, HEAD, OPTIONS, PATCH, DELETE, TRACE
- params: los parametros de la peticion
- headers: cabeceras a las que responde el metodo
- consumes: el tipo de soportes que consume el metodo
- produces: el tipo de soporte que produce el metodo


@Id
@GeneratedValue(strategy=GenerationType.IDENTITY)

opcines

- AUTO
- TABLE
- SECUENCE
- IDENTITY

@Column

parametros:

- unique
- nullable
- updatable: especifica si se incluye en operaciones UPDATE por defecto true
- columnDefinition: especifica el tipo
- table: especifica la tabla en la que se encuentra
- length: especifica la longitud de la columna por defecto 255
- precision: especifica la precision decimal por defecto 0
- scale: la escala de un numerico por defecto 0

Todos los metodos comienzan por findBy y una propiedad del objeto buscado, seguido de mas opciones que se especifican mediante palabras clave son:
And, Or, Between, LessThan, GreaterThan, After, Before, IsNull, IsNotNull, Like, NotLike, StartingWith, EndingWWith, Containing, OrderBy, Not, In, NotIn, True, False, IgnoreCase.

Ejemplo:
findByLastnameAndFirstname
findByAgeOrderByLastnameDesc
findByActiveTrue

## Query mediante anotaciones

permitiendo añadir anotaciones en la entidad que se resuelven en tiempo de compilacion
@NamedQuery(name="User.findByEmail", query="select u from usr u where u.email = ?1")

# application.properties

spring.datasource.url: jdbc:mysql://localhost:3306/spring_demo
spring.datasource.username:root
spring.datasource.password:
spring.datasource.driverClassName: com.mysql.jdbc.Driver

spring.jpa.hibernate.ddl-auto:update
spring.jpa.database:MYSQL

# REQUISITOS

Se va a desarrollar una aplicacion web encargada de gestionar una comunidad de usuarios que comparten recetas de cocina. La aplicacion sera capaz de gestionar tanto a los usuarios que interactuan con la aplicacion como a los 
recursos utilizados para conseguir el objetivo. Los usuarios pueden ser administradores o usuarios comunes. Los recursos son las recetas y sus componentes. Los usuarios comunes seran capaces de gestionar sus propios datos y recetas
y podran ver los datos y recetas de los demas. El administrador tendra la capacidades de un usuario comun, ademas de una serie de privilegios adicionales.

Los usuarios prodran realizar las siguientes tareas:
- registrarse
- verificar su cuenta
- ver sus datos y otros usuarios
- modificar sus datos
- crear recetas
- ver sus recetas y las de los demas usuarios
- buscar recetas
- modificar y borrar sus recetas

El administrador podra realizar las mismas acciones que un usuario comun ademas de las siguientes:
- ver una lista de usuarios
- modificar datos de usuarios
- bloquear y desbloquear usuarios
- dar y quitar permisos de administracion
- modificar recetas de otros usuarios
- borrar recetas de otros usuarios


# View Resolves

son objectos que implementan la interfaz ViewResolver. devuelven la vista template dependiendo del nombre
