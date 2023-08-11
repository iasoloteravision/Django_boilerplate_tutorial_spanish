## Django boilerplate

Un "boilerplate" es una plantilla predefinida que contiene una estructura y configuración básica para un tipo específico de proyecto. Aquí te proporciono un diseño de boilerplate para un proyecto con Django, que incluye una estructura básica y algunas configuraciones iniciales:

**Estructura de directorios y archivos:**

```
mi_proyecto_django/
├── apps/
│   ├── core/
│   │   ├── migrations/
│   │   ├── static/
│   │   ├── templates/
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── models.py
│   │   ├── tests.py
│   │   └── views.py
│   └── blog/
│       ├── migrations/
│       ├── static/
│       ├── templates/
│       ├── __init__.py
│       ├── admin.py
│       ├── apps.py
│       ├── models.py
│       ├── tests.py
│       └── views.py
├── mi_proyecto/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
├── static/
├── templates/
├── venv/
├── .gitignore
├── manage.py
└── README.md
```

**Pasos para configurar el boilerplate:**

1. Crea un nuevo directorio para tu proyecto:
   ```bash
   mkdir mi_proyecto_django (Aqui es donde pones el nombre al proyecto)
   cd mi_proyecto_django
   ```

2. Crea un entorno virtual y actívalo una vez dentro del nuevo directorio:
   ```bash
   python -m venv venv
   source venv/bin/activate  # En macOS y Linux
   venv\Scripts\activate     # En Windows
   ```

3. Instala Django:
   ```bash
   pip install django
   ```

4. Crea un nuevo proyecto y una aplicación inicial:
   ```bash
   django-admin startproject mi_proyecto (nombra tu proyecto) .
   cd mi_proyecto
   python manage.py startapp core (aplicaciones de tu proyecto)
   python manage.py startapp blog
   ```

5. Copia y pega la estructura de directorios y archivos proporcionada arriba en tu directorio raíz    `mi_proyecto_django`.

6. Asegúrate de que `INSTALLED_APPS` en `settings.py` incluya las aplicaciones que creaste:
   ```python
   INSTALLED_APPS = [
       ...
       'apps.core',
       'apps.blog',
       ...
   ]
   ```

7. Configura la zona horaria y la base de datos en `settings.py`.

8. Configura la carpeta de plantillas y los archivos estáticos en `settings.py`:
   ```python
   TEMPLATES = [
       {
           ...
           'APP_DIRS': True,
           ...
       }
   ]

   STATIC_URL = '/static/'
   STATICFILES_DIRS = [BASE_DIR / "static"]
   ```

9. Crea tus modelos en las aplicaciones `core` y `blog`, luego ejecuta las migraciones: [Definir modelos en Django](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Definir%20modelos%20en%20Django.md)
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

10. Define las rutas y vistas en `urls.py` en el directorio `mi_proyecto`. [Definir rutas en Django](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Definir%20rutas%20en%20Django.md) [Definir vistas en Django](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Definir%20vistas%20en%20Django.md)

11. Agrega tus archivos estáticos (CSS, JavaScript, imágenes) en las carpetas `static` dentro de cada aplicación. [Agregar archivos estáticos](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Agregar%20archivos%20est%C3%A1ticos.md)

12. Crea tus plantillas HTML en las carpetas `templates` dentro de cada aplicación. [Crear plantillas HTML](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Crear%20plantillas%20HTML.md)

13. Desarrolla tus vistas y funcionalidades en las aplicaciones `core` y `blog`. [Desarrollar vistas y funcionalidades en las aplicaciones Django](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Desarrollar%20vistas%20y%20funcionalidades%20en%20las%20aplicaciones%20Django.md)

14. Crea un superusuario para acceder al panel de administración: [Crear superusuario en Django](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Crear%20superusuario%20en%20Django.md)
    ```bash
    python manage.py createsuperuser
    ```

15. ¡Listo! Ahora puedes comenzar a desarrollar tu proyecto Django basado en este boilerplate.

Este boilerplate te proporciona una estructura inicial para tu proyecto Django y está listo para ser personalizado y ampliado según tus necesidades específicas. A medida que agregues más funcionalidades y aplicaciones, asegúrate de mantener una estructura modular y mantener tus archivos bien organizados.