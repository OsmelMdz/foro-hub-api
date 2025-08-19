# Curso Practicando Spring Framework: Challenge Foro Hub

Este repositorio contiene el proyecto de una API REST para la gestión de tópicos en un foro, desarrollada como parte del Challenge Alura.
La API permite realizar operaciones CRUD sobre los tópicos y autenticar usuarios mediante JWT para garantizar seguridad.

## Características principales
- Listar todos los tópicos
- Crear un nuevo tópico
- Actualizar un tópico existente
- Eliminar un tópico
- Autenticación segura de usuarios con JWT

## Tecnologías y herramientas utilizadas
- Java 17+
- Spring Boot (Spring Web, Spring Security, Spring Data JPA)
- Base de datos: MySQL | PostgreSQL | H2 (para pruebas)
- Maven para la gestión de dependencias
- JWT para autenticación
- Insomnia o Postman para pruebas de la API

## Cómo ejecutar el proyecto
1. Clona este repositorio en tu máquina local.
2. Abre el proyecto con IntelliJ IDEA.
3. Configurar la base de datos en src/main/resources/application.properties:
   spring.datasource.url=jdbc:mysql://localhost/nombre_de_tu_bd?createDatabaseIfNotExist=true
   spring.datasource.username=tu_usuario
   spring.datasource.password=tu_contraseña
   spring.jpa.hibernate.ddl-auto=update
4. Ejecutar migraciones (si aplicaste Flyway o Liquibase).
5. Iniciar el proyecto:
   mvn spring-boot:run
La API estará disponible en:
http://localhost:8080

## Endpoints principales
### Tópicos:
- GET /topicos → Lista todos los tópicos
- POST /topicos → Crea un nuevo tópico (requiere JWT)
- PUT /topicos/{id} → Actualiza un tópico (requiere JWT)
- DELETE /topicos/{id} → Elimina un tópico (requiere JWT)

## Autenticación:
- POST /auth → Autentica un usuario y devuelve el token JWT

## Ejemplos de uso
Listar tópicos:
- GET http://localhost:8080/topicos

Crear un tópico (requiere JWT):
- POST http://localhost:8080/topicos
Headers:
Authorization: Bearer <JWT_TOKEN>
Content-Type: application/json

Body:
{
"usuarioId": 1,
"titulo": "Nueva duda",
"mensaje": "Tengo una pregunta sobre...",
"curso": "SpringBoot"
}

## Prerrequisitos
- Tener instalado Java 17 o superior
- Tener Maven configurado
- Base de datos activa y credenciales correctas en application.properties

## Arquitectura
Este proyecto sigue las buenas prácticas de arquitectura en capas:
- Controller → Gestión de endpoints
- Service → Lógica de negocio
- Repository → Acceso a datos
- Security → Configuración JWT y autenticación

Proyecto desarrollado para el Challenge Alura en el curso:
"Practicando Spring Framework: Challenge Foro Hub"

## Instructor
**Génesys Rondón**  
Ingeniera de Sistemas, especializada en desarrollo web Back End.  
Con experiencia en Java, C#, C++, JavaScript, Node.js, Spring y ASP.NET Core.  
Amante de los gatos, los videojuegos y la literatura clásica.  
LinkedIn: https://www.linkedin.com/in/genesysrondon914762182/  
GitHub: https://github.com/genesysR-dev
