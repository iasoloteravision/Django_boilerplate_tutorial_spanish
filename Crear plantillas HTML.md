Crear plantillas HTML en tu proyecto Django es fundamental para lograr una estructura consistente y reutilizable en tus páginas web. Las plantillas te permiten separar el diseño y la estructura HTML de los datos dinámicos que se mostrarán en esas páginas. Aquí te explico cómo crear y utilizar plantillas HTML en el proyecto que hemos estado construyendo:

**Paso 1: Estructura de Directorios:**

Asegúrate de que tu proyecto tenga una estructura similar a esta:

```
mi_proyecto_django/
├── apps/
│   ├── core/
│   │   ├── ...
│   │   ├── static/
│   │   ├── templates/
│   └── blog/
│       ├── ...
│       ├── static/
│       ├── templates/
├── static/
└── templates/
```

**Paso 2: Crear Plantillas HTML:**

1. Crea una carpeta llamada `templates` dentro de cada aplicación (`apps/core/templates/core/` y `apps/blog/templates/blog/`).

2. Dentro de estas carpetas, crea archivos HTML para cada vista que has definido. Por ejemplo, si tienes una vista `home`, crea un archivo `home.html` dentro de la carpeta `templates` correspondiente.

3. En tus archivos HTML, puedes utilizar código HTML estándar junto con etiquetas y variables de plantilla de Django para renderear datos dinámicos.

**Paso 3: Uso de Etiquetas y Variables de Plantilla:**

En las plantillas HTML, puedes usar etiquetas y variables de plantilla de Django para renderizar contenido dinámico. Por ejemplo, puedes usar la etiqueta `{% for %}` para iterar sobre una lista de elementos y la etiqueta `{% if %}` para aplicar lógica condicional.

Aquí hay un ejemplo simple de cómo usar estas etiquetas en una plantilla:

```html
{% for post in posts %}
    <h2>{{ post.title }}</h2>
    <p>{{ post.content }}</p>
{% endfor %}
```

En este ejemplo, `posts` es una lista de objetos que se pasará desde la vista a la plantilla. La etiqueta `{% for %}` itera sobre cada objeto en la lista y muestra su título y contenido.

**Paso 4: Extender Plantillas Base:**

Django te permite crear plantillas base que definen la estructura común de tus páginas web y luego extenderlas en plantillas específicas para añadir contenido único. Esto ayuda a mantener una estructura coherente en todo tu sitio web.

Por ejemplo, podrías tener una plantilla base `base.html` con la estructura HTML común, y luego extenderla en plantillas específicas:

```html
<!-- base.html -->
<!DOCTYPE html>
<html>
<head>
    <title>{% block title %}Mi Sitio Web{% endblock %}</title>
</head>
<body>
    <div id="header">
        <!-- Contenido del encabezado -->
    </div>
    
    <div id="content">
        {% block content %}
        <!-- Contenido de la página -->
        {% endblock %}
    </div>
    
    <div id="footer">
        <!-- Contenido del pie de página -->
    </div>
</body>
</html>
```

```html
<!-- home.html (extiende de base.html) -->
{% extends "base.html" %}

{% block title %}Página de Inicio{% endblock %}

{% block content %}
    <h1>Bienvenido a mi sitio web</h1>
    <p>Esta es la página de inicio.</p>
{% endblock %}
```

**Resumen:**

Crear plantillas HTML en tu proyecto Django implica crear archivos HTML en las carpetas `templates` de cada aplicación. Puedes usar etiquetas y variables de plantilla de Django para renderizar contenido dinámico y crear estructuras comunes en tus páginas. Además, puedes extender plantillas base para mantener una estructura coherente en todo tu sitio web mientras personalizas el contenido en páginas específicas. Las plantillas te permiten separar el diseño y la estructura HTML de los datos dinámicos, lo que hace que tu aplicación sea más organizada y fácil de mantener.

[[Django Boilerplate]]