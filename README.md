# 📘 Personal Blog - Despliegue Dockerizado

Este proyecto es una aplicación de Blog desarrollada en **Django**, configurada para un entorno de producción utilizando **Docker** y **Nginx** como proxy inverso, siguiendo las pautas de arquitectura de las páginas 110-123 de la documentación de la asignatura.

## 🚀 Arquitectura del Sistema

Siguiendo las pautas de "Best Practices" (Pág. 117-122), el sistema se divide en dos servicios principales:

* **Contenedor Web (Django + Gunicorn):** Ejecuta la lógica de la aplicación. Se ha eliminado el servidor de desarrollo y el `django-browser-reload` para optimizar el rendimiento y evitar "malas praxis" en producción.
* **Contenedor Nginx:** Actúa como servidor frontal. Gestiona las peticiones HTTP, sirve directamente los archivos estáticos y media, y redirige el resto del tráfico a Gunicorn.

## 🛠️ Requisitos
* Docker Desktop con motor WSL2.
* Archivo de variables de entorno `.env` configurado.

## 📦 Instalación y Despliegue

### 1. Construcción del Entorno
Ejecuta el siguiente comando para construir las imágenes y levantar los servicios en segundo plano:
```bash
docker-compose up --build -d
