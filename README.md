# Django Documentation
```
django-admin startproject \[nome-do-seu-projeto]

cd nome-do-seu-projeto

python manage.py startapp \[nome-do-app]
```

<br><br>

### Para Criar uma View

Dentro de views.py, podemos definir uma View através de uma função ou através de uma classe.

from django.http import HttpResponse
from django.views import View

def hello_world(request):
  return HttpResponse("Hello world!")

class HelloWorld(View):
  def get(self, request):
    return HttpResponse("Hello world!")

<br><br>

### Para configurar os endereços das Views

Dentro de urls.py, podemos importar as views do próprio app ou de um outro app usando include.

from django.urls import path, include
from . import views

urlpatterns = \[
  path('yourUrl', views.hello_world),
  path('anotherUrl', views.HelloWorld.as_views(),
  path('app/', include('yourapp.urls')),
]

<br><br>

### Para instalar os apps no app principal

Dentro de settings.py do app principal, adicionar os apps secundários em INSTALLED_APPS.

INSTALLED_APPS = \[
  'yourapp',
]

<br><br>

### Para rodar

python manage.py runserver



 
