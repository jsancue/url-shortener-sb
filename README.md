# 📎 URL Shortener - Spring Boot

Este proyecto es un acortador de URLs desarrollado con Spring Boot. Permite convertir URLs largas en enlaces cortos y redirigirlas correctamente, ideal como herramienta de aprendizaje sobre desarrollo web, persistencia y APIs REST.
Repositorio del Frontend: https://github.com/jsancue/url-short-react

## 🚀 Características

- Acorta URLs largas en enlaces breves.
- Redirección automática al acceder al enlace corto.
- Persistencia de URLs en base de datos.
- API REST para crear y acceder a las URLs.
- Interfaz minimalista (si aplica).
- Arquitectura limpia y modular.

## 🛠️ Tecnologías utilizadas

- Java 23
- Spring Boot
- Spring Security
- Spring Data JPA
- PostgreSQL Database
- JSON Web Tokens (JWT)
- Lombok
- Maven

## 📦 Instalación y ejecución

### Prerrequisitos

- JDK 23 o superior
- Maven

### Clonar el repositorio

```bash
git clone https://github.com/jsancue/url-shortener-sb.git
cd url-shortener-sb
```

### Ejecutar la aplicación

```bash
./mvnw spring-boot:run
```

O si prefieres usar Maven directamente:

```bash
mvn spring-boot:run
```

La aplicación estará disponible en: `http://localhost:8080`

## 📌 Endpoints principales

### Crear una URL corta

```http
POST /api/shorten
Content-Type: application/json

{
  "url": "https://ejemplo.com/mi-url-larga"
}
```

**Respuesta:**

```json
{
  "shortUrl": "http://localhost:8080/abc123"
}
```

### Redirigir desde una URL corta

```http
GET /abc123
```

Redirige automáticamente a `https://ejemplo.com/mi-url-larga`.

## 🧪 Pruebas

Puedes probar los endpoints usando Postman, curl o tu navegador.

## 🗂 Estructura del proyecto

```
src/
└── main/
    ├── java/com/example/urlshortener/
    │   ├── controllers/
    │   ├── dtos/
    │   ├── models/
    │   ├── repository/
    │   ├── security/
    │   ├── service/
    │   └── UrlShortenerApplication.java
    └── resources/
        ├── application.properties
        └── static/
```


## 🐳 Despliegue con Docker

Este proyecto incluye un `Dockerfile` para facilitar su despliegue en contenedores.

### Construir la imagen

```bash
docker build -t url-shortener-sb .
```

### Ejecutar el contenedor

```bash
docker run -d -p 8080:8080 --name url-shortener url-shortener-sb
```

La aplicación estará disponible en: `http://localhost:8080`

### Ver logs del contenedor

```bash
docker logs -f url-shortener
```

### Detener y eliminar el contenedor

```bash
docker stop url-shortener && docker rm url-shortener
```

## 🧑‍💻 Autor

- [jsancue](https://github.com/jsancue)

## 📝 Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más información.

---

¡Gracias por visitar el proyecto! Si te resultó útil, considera darle una ⭐ en GitHub.
