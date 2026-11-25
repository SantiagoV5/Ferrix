# Ferrix

Sistema de gestión de productos e inventarios con control de acceso por perfiles (vendedor y administrador), construido con Spring Boot bajo arquitectura de microservicios y desplegado con Docker.

> Proyecto final de **Desarrollo de Software III** — Universidad del Valle, Sede Tuluá.

## Perfiles

- **Vendedor:** consulta productos y disponibilidad, y registra movimientos de inventario.
- **Administrador:** gestiona productos, inventario y usuarios.

## Arquitectura

Cada microservicio corre en su propio contenedor y todas las peticiones entran por el API Gateway.

| Servicio | Función |
|----------|---------|
| `api-gateway` | Punto de entrada único (patrón API Gateway) |
| `auth-service` | Usuarios, autenticación y roles |
| `product-service` | Catálogo de productos |
| `inventory-service` | Stock y movimientos de inventario |

Cada servicio sigue el patrón **DTO + Service + Repository**.

## Modelo de datos

| Tabla | Descripción |
|-------|-------------|
| `usuarios` | Usuarios y rol (vendedor / administrador) |
| `productos` | Catálogo de productos |
| `movimientos_inventario` | Entradas y salidas, con FK a `productos` y `usuarios` |
| `alertas_stock` | Alertas por stock bajo, con FK a `productos` |

> Modelo preliminar, sujeto a ajustes durante el desarrollo.

## Tecnologías

- Java + Spring Boot (Spring Web, Spring Data JPA)
- MySQL o PostgreSQL (por definir)
- Frontend: Thymeleaf o React (por definir)
- Docker y Docker Compose
- Git y GitHub

## Ejecución

Requisitos: Docker y Docker Compose.

```bash
git clone https://github.com/TU_USUARIO/ferrix.git
cd ferrix
docker compose up --build
```

Los datos iniciales se cargan automáticamente al levantar los servicios.

## Estructura del repositorio

```
ferrix/
├── api-gateway/
├── auth-service/
├── product-service/
├── inventory-service/
├── frontend/
├── docker-compose.yml
└── README.md
```

## Equipo

- Santiago — [@TU_USUARIO](https://github.com/TU_USUARIO)

## Licencia

Distribuido bajo licencia MIT. Ver [LICENSE](LICENSE).
