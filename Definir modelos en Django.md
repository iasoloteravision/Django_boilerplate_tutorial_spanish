Los modelos en Django son clases de Python que definen la estructura de la base de datos. Cada modelo se convierte en una tabla en la base de datos y sus atributos representan las columnas de esa tabla.

En nuestro boilerplate, vamos a crear modelos en las aplicaciones `core` y `blog`:

1. Abre el archivo `models.py` dentro de la aplicación `core` (`apps/core/models.py`).
2. Define un modelo simple, por ejemplo, un modelo `Post` para representar entradas de blog:

~~~
from django.db import models

class Post(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    pub_date = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title
~~~

Realiza el mismo proceso en la aplicación `blog` para definir cualquier otro modelo que necesites.

[[Django Boilerplate]]