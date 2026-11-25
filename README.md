# Ferrix

Sistema de gestión de productos e inventarios con control de acceso por perfiles. Permite administrar el catálogo, el stock y las operaciones de venta desde una arquitectura de microservicios.

## Perfiles

- **Vendedor:** consulta productos y disponibilidad, registra ventas y revisa su historial.
- **Administrador:** gestiona productos, inventario, usuarios y reportes.

## Tecnologías

- Java + Spring Boot
- Arquitectura de microservicios
- Docker y Docker Compose
- Base de datos relacional (ajustar según el proyecto)

## Microservicios

| Servicio | Función |
|----------|---------|
| `auth-service` | Autenticación y roles |
| `product-service` | Catálogo de productos |
| `inventory-service` | Control de stock |
| `api-gateway` | Punto de entrada único |

> Ajustar la tabla a los servicios reales del proyecto.

## Ejecución

```bash
git clone https://github.com/TU_USUARIO/ferrix.git
cd ferrix
docker compose up --build
```

## Equipo

- Santiago — [@TU_USUARIO](https://github.com/TU_USUARIO)

## Licencia

Distribuido bajo licencia MIT. Ver [LICENSE](LICENSE).
