 En Django, las "rutas" se refieren a las URL (Uniform Resource Locator) o direcciones web que los usuarios pueden utilizar para acceder a diferentes páginas y recursos en tu aplicación web. Las rutas en Django permiten mapear las solicitudes de los usuarios a funciones de vista específicas que generan una respuesta, como una página web renderizada.

En términos más sencillos, las rutas definen cómo se navega y se accede a diferentes partes de tu aplicación. Cada ruta está asociada a una vista en Django, que es una función o una clase que se encarga de procesar la solicitud y devolver una respuesta.

Definir rutas  en Django es fundamental para determinar cómo se manejarán las solicitudes de los usuarios y qué contenido se mostrará en respuesta a esas solicitudes. A continuación, te explicaré cómo definir rutas y vistas en el proyecto con el boilerplate que creamos:

**Definir Rutas (URLs):**

Las rutas en Django se definen en el archivo `urls.py` de cada aplicación para especificar cómo se deben manejar las solicitudes entrantes. Aquí tienes los pasos para definir rutas:

1. Abre el archivo `urls.py` dentro de la aplicación `core` (`apps/core/urls.py`).

2. Importa las vistas que has definido en `views.py`:
   ```python
   from django.urls import path
   from . import views
   ```

3. Define las rutas utilizando la función `path()` y asigna las vistas correspondientes:
   ```python
   app_name = 'core'

   urlpatterns = [
       path('', views.home, name='home'),
       path('about/', views.about, name='about'),
   ]
   ```

4. Repite el proceso para la aplicación `blog` (`apps/blog/urls.py`), definiendo las rutas específicas de esa aplicación.

[[Django Boilerplate]]