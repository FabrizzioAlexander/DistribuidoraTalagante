## Desplegado en Render - Titulación 2025
# Distribuidora Talagante

Sistema de gestión y ventas para distribuidora de productos alimenticios (lácteos, cecinas, congelados, etc.), desarrollado como proyecto de titulación.

## Descripción del Proyecto

Este proyecto es un sistema web completo para la administración de una distribuidora. Permite gestionar productos, controlar el inventario, realizar ventas tanto al por mayor como al detalle, y administrar pedidos y clientes.

El enfoque principal fue construir un backend robusto con APIs REST que puedan ser consumidas por un frontend web o aplicaciones móviles en el futuro.

## Aspectos Técnicos

**Tecnologías utilizadas:**

- **Backend**: Django + Django REST Framework (DRF)
- **Base de datos**: SQLite (desarrollo) y compatible con PostgreSQL
- **Autenticación**: Sistema propio de registro y login con verificación por correo electrónico y SMS (Twilio)
- **Mensajería**: API de mensajería integrada para notificaciones
- **Contenerización**: Docker + Docker Compose
- **Servidor web**: Nginx (configuración para producción)
- **Despliegue**: Render

**Estructura principal:**

- `core/`: Aplicación principal donde se encuentran los modelos, serializers, vistas y lógica del negocio.
- `distribuidora/`: Configuración del proyecto Django.
- `fixtures/`: Datos iniciales para cargar productos y usuarios de prueba.
- `media/`: Almacenamiento de imágenes de productos.
- `nginx/`: Configuración del servidor web.

## Funcionalidades Principales

- APIs REST completas para productos, clientes, pedidos e inventario.
- Gestión de stock con control de entradas y salidas.
- Sistema de verificación de usuarios por email y SMS.
- Panel de administración avanzado.
- Carga y gestión de imágenes de productos.
- Preparado para escalar agregando un frontend separado (React/Vue).

## Cómo ejecutar el proyecto localmente

```bash
# Clonar repositorio
git clone https://github.com/FabrizzioAlexander/DistribuidoraTalagante.git

cd DistribuidoraTalagante

# Opción recomendada: con Docker
docker-compose up --build

# Opción manual
python -m venv venv
source venv/bin/activate    # En Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
