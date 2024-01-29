# Documentación de Código

## `PersonExtension.kt`

Este archivo contiene extensiones de Kotlin para convertir entre objetos `Person` y `PersonDto`.

- `fun Person.toDto(): PersonDto`: Convierte un objeto `Person` en un objeto `PersonDto`.
- `fun PersonDto.toPerson(): Person`: Convierte un objeto `PersonDto` en un objeto `Person`.

## `ErrorResponse.kt`

Este archivo define un modelo de datos `ErrorResponse` que se utiliza para representar mensajes de error.

- `data class ErrorResponse(val message: String)`: Define un modelo de error con un mensaje.
- `companion object`: Contiene dos instancias predefinidas de `ErrorResponse` para "No encontrado" y "Solicitud inválida".

## `Person.kt`

Este archivo define el modelo de datos `Person`.

- `data class Person`: Define un modelo de datos para una persona con un identificador, nombre y edad.

## `PersonDto.kt`

Este archivo define el modelo de datos `PersonDto`, que se utiliza para transferir datos de persona.

- `data class PersonDto`: Define un modelo de datos para una persona con un identificador, nombre y edad.

## `Application.kt`

Este archivo es el punto de entrada de la aplicación y configura el servidor Ktor.

- `fun main()`: Inicializa el servidor Ktor en el puerto 8080 y configura el enrutamiento y la serialización.

## `PersonService.kt`

Este archivo contiene la lógica de negocio para interactuar con objetos `Person` en una base de datos MongoDB.

- `class PersonService`: Contiene métodos para crear, buscar, actualizar y eliminar personas en la base de datos.

## `Routing.kt`

Este archivo configura las rutas y el manejo de las solicitudes relacionadas con las personas en la aplicación.

- `fun Application.configureRouting()`: Configura las rutas y las operaciones para crear, leer, actualizar y eliminar personas.

## `Serialization.kt`

Este archivo configura la serialización JSON para la aplicación Ktor.

- `fun Application.configureSerialization()`: Configura la serialización JSON para la aplicación.

# ¿Como se usa?

## Proyecto de Gestión de Personas

Este proyecto es una aplicación de gestión de personas construida con Ktor y MongoDB. Permite crear, leer, actualizar y eliminar registros de personas y responde a solicitudes JSON.

### Cómo crear el proyecto

1. Asegúrate de tener instalados Kotlin, Ktor y MongoDB en tu entorno de desarrollo.

2. Crea una nueva aplicación de Kotlin utilizando la plantilla de Ktor.

3. Agrega las dependencias necesarias en el archivo `build.gradle.kts`.

4. Crea los archivos de código proporcionados en la estructura de carpetas adecuada.

5. Configura la conexión a la base de datos MongoDB en `PersonService.kt`.

6. Ejecuta la aplicación con `Application.kt` como punto de entrada.

### Cómo funciona la aplicación

La aplicación expone una API REST para gestionar personas. Utiliza extensiones para convertir entre objetos `Person` y `PersonDto`. La lógica de negocio se encuentra en `PersonService.kt`, donde se pueden realizar operaciones de creación, lectura, actualización y eliminación en la base de datos MongoDB.

La configuración de las rutas y la serialización se realiza en `Routing.kt` y `Serialization.kt`, respectivamente. Los mensajes de error se gestionan con el modelo `ErrorResponse`.

### Rutas disponibles

- `POST /person`: Crea una nueva persona.
- `GET /person`: Obtiene la lista de todas las personas.
- `GET /person/{id}`: Obtiene los detalles de una persona por su ID.
- `PUT /person/{id}`: Actualiza los detalles de una persona por su ID.
- `DELETE /person/{id}`: Elimina una persona por su ID.

### Modelos de datos

- `Person`: Representa una persona con un identificador, nombre y edad.
- `PersonDto`: Utilizado para transferir datos de persona.
- `ErrorResponse`: Representa un mensaje de error con un campo de mensaje.

Este README proporciona una visión general del proyecto. Para detalles de implementación, consulta la documentación en los archivos de código fuente.

¡Disfruta trabajando en tu proyecto de gestión de personas con Ktor!
