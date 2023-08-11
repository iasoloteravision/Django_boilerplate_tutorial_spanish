Agregar archivos estáticos a tu proyecto Django es esencial para proporcionar estilos CSS, scripts JavaScript e imágenes que se utilizan en tus plantillas HTML. Los archivos estáticos son aquellos que no cambian según la solicitud del usuario, a diferencia de las vistas dinámicas que generan contenido diferente en función de los datos o parámetros de la solicitud.

Aquí te explico cómo agregar archivos estáticos a tu proyecto utilizando el boilerplate que creamos anteriormente:

**Paso 1: Estructura de Directorios:**

Asegúrate de que tu proyecto tenga una estructura similar a esta:

```
mi_proyecto_django/
├── apps/
│   ├── core/
│   │   ├── ...
│   │   ├── static/
│   │   └── templates/
│   └── blog/
│       ├── ...
│       ├── static/
│       └── templates/
├── static/
└── templates/
```

**Paso 2: Configuración de Archivos Estáticos:**

1. Abre el archivo `settings.py` en el directorio `mi_proyecto` (`mi_proyecto_django/mi_proyecto/settings.py`).

2. Busca la configuración `STATIC_URL` y asegúrate de que esté configurada correctamente. Por defecto, debería ser:
   ```python
   STATIC_URL = '/static/'
   ```

3. Justo después de `STATIC_URL`, agrega la siguiente línea para indicar a Django dónde buscar los archivos estáticos en tu proyecto:
   ```python
   STATICFILES_DIRS = [BASE_DIR / "static"]
   ```

**Paso 3: Agregar Archivos Estáticos:**

1. Crea una carpeta llamada `static` en el directorio raíz de tu proyecto (`mi_proyecto_django/static/`).

2. Dentro de la carpeta `static`, puedes organizar tus archivos en subcarpetas según el tipo de contenido, como `css`, `js` e `images`.

3. Agrega tus archivos estáticos a las subcarpetas apropiadas. Por ejemplo, si tienes un archivo CSS llamado `styles.css`, puedes colocarlo en `mi_proyecto_django/static/css/styles.css`.

**Paso 4: Referenciar Archivos Estáticos en Plantillas:**

En tus plantillas HTML, puedes utilizar la etiqueta `{% static 'ruta_del_archivo' %}` para hacer referencia a los archivos estáticos. Por ejemplo:

```html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="{% static 'css/styles.css' %}">
</head>
<body>
    <!-- Contenido de la plantilla -->
</body>
</html>
```

**Paso 5: Incluir Archivos Estáticos en Plantillas:**

Para que los archivos estáticos se carguen correctamente en tus plantillas, asegúrate de que las plantillas tengan una etiqueta `{% load static %}` al comienzo. Por ejemplo:

```html
{% load static %}
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="{% static 'css/styles.css' %}">
</head>
<body>
    <!-- Contenido de la plantilla -->
</body>
</html>
```

**Resumen:**

Agregar archivos estáticos a tu proyecto Django implica configurar la ruta de archivos estáticos en `settings.py`, crear una estructura de carpetas en el directorio `static`, y luego referenciar y cargar estos archivos en tus plantillas HTML. Los archivos estáticos permiten mejorar la apariencia y la interactividad de tus páginas web al proporcionar estilos CSS, scripts JavaScript e imágenes.
[Django Boilerplate](https://github.com/iasoloteravision/Django_boilerplate_tutorial_spanish/blob/main/Django%20Boilerplate.md)
