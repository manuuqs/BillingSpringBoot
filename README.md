# Billing API - Spring Boot Project

## Descripción

Este proyecto es una aplicación de facturación desarrollada con **Spring Boot** que expone una API REST para la gestión de facturas. Incluye documentación automática con **OpenAPI/Swagger**, soporte para bases de datos relacionales y buenas prácticas para el desarrollo de aplicaciones Java.

## Características principales

- **Framework principal**: Spring Boot 2.7.5.
- **Gestor de dependencias**: Maven.
- **Base de datos**: PostgreSQL (principal) y H2 (para pruebas en memoria).
- **Documentación interactiva**: Generada con `springdoc-openapi-ui`.
- **Testing**: Incluye soporte para pruebas unitarias con JUnit.
- **Reducción de boilerplate**: Uso de Lombok para simplificar código repetitivo.

## Tecnologías utilizadas

- **Java 17**
- **Spring Boot**:
  - Spring Boot Starter Web (API REST)
  - Spring Boot Starter Data JPA (Persistencia de datos)
  - Spring Boot DevTools (Herramientas de desarrollo)
- **Bases de datos**:
  - PostgreSQL
  - H2 (para pruebas)
- **Swagger/OpenAPI**: Para documentar y probar la API.
- **Lombok**: Para simplificar código repetitivo (Getters/Setters).
- **JUnit**: Para pruebas.

## Requisitos previos

Asegúrate de tener instalados los siguientes programas:

- Java 17 o superior.
- Maven 3.6 o superior.
- PostgreSQL configurado y en ejecución.

## Configuración del proyecto

1. Clona este repositorio:

   ```bash
   git clone https://github.com/tu-usuario/billing_openAPI.git
   cd billing_openAPI
   ```

2. Configura la base de datos PostgreSQL en el archivo `application.properties`:

   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/nombre_base_datos
   spring.datasource.username=tu_usuario
   spring.datasource.password=tu_contraseña
   spring.jpa.hibernate.ddl-auto=update
   spring.sql.init.mode=always
   ```

3. Construye el proyecto con Maven:

   ```bash
   mvn clean install
   ```

4. Ejecuta la aplicación:

   ```bash
   mvn spring-boot:run
   ```

## Endpoints principales

Una vez que la aplicación esté en ejecución, puedes acceder a la documentación de la API:

- **Swagger/OpenAPI UI**: [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

### Ejemplo de endpoints:

- `GET /invoices` - Obtiene todas las facturas.
- `POST /invoices` - Crea una nueva factura.
- `GET /invoices/{id}` - Obtiene una factura por su ID.

## Estructura del proyecto

```
src/
├── main/
│   ├── java/com/paymentchain/billing/
│   │   ├── controller/  # Controladores REST
│   │   ├── entities/    # Clases de entidades (JPA)
│   │   ├── repository/  # Interfaces de repositorio
│   │   ├── exception/   # Manejo de excepciones personalizadas
│   │   └── InvoiceApplication.java  # Clase principal
│   └── resources/
│       ├── application.properties  # Configuración
├── test/  # Pruebas unitarias
└── pom.xml  # Archivo Maven
```

## Compilación y empaquetado

Para generar el archivo JAR ejecutable:

```bash
mvn package
```

El archivo resultante estará en la carpeta `target/` con el nombre `billing-0.0.1-SNAPSHOT.jar`.

Para ejecutar el JAR:

```bash
java -jar target/billing-0.0.1-SNAPSHOT.jar
```

##

