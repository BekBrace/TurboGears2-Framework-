<h1> TurboGears2 ⚙️ Full-Stack Framework for Python </h1> 

A quick introduction about TurboGears2 , a full-stack framework for Python


TurboGears is a full-stack framework, a battery-included framework in other workds ..actually this is TurboGears 2 which

is a reinvention of the original turbogears project to make use of the new components and give you a fully customizable WSGI server.

A minimal installation of TurboGears is done by 

>>> pip install TurboGears2

To install TurboGears along with development tools, use 
>>> pip install tg.devtools

Before, it's better to setup a virtual enviornment by using 

>>> pipenv shell

to activate the virtual enviornment, and if you don't have pipenv, you can install simply by:

>>> pip install pipenv

TurboGears has a minimal mode that makes it possible to create single file applications quickly. 

Simple examples and services can be built quickly with minimal set of dependencies.

from tg import expose, TGController

A class in a turbogears application is inherited from TGController Parent class.
class MyController(TGController):

Methods in this class are available for access by @expose decorator from tg module.
   @expose()

In our first application, index() method is mapped as root of our application. The TGController class also needs to be imported from tg module.
   def index(self):
      return 'Hello, TurboGears'

config = AppConfig(minimal = True, root_controller = MyController())

The make_wsgi_app() function here constructs application object.

application = config.make_wsgi_app()

In order to serve this application, we  need to start the HTTP server. 

You can use simple_server module in wsgiref package to set up and start it.  

from wsgiref.simple_server import make_server

This module has make_server() method which requires port number and application object as arguments.

server = make_server('', 8080, application)
server.serve_forever()
      
 Then run your app 
 >>> python main.py 
 
 Nothing will tell you that the app is running on whatever port , so you'll need to open the browser and check out on port 8080.
 
 
*****************
Full-Stack Setup:
*****************
The tg.devtools of TurboGears contains Gearbox. 

It is a set of commands, which are useful for management of more complex TG projects.

Full stack projects can be quickly created by the following Gearbox command 

>>> gearbox quickstart HelloWorld

This will create a project called HelloWorld

A TurboGears project contains the following directories −

Config − Where project setup and configuration relies

Controllers − All the project controllers, the logic of web application

i18n − Translation files for the languages supported

Lib − Utility python functions and classes

Model − Database models

Public Static Files − CSS, JavaScript and images

Templates − Templates exposed by our controllers.

Tests − The set of Tests done.

Websetup − Functions to execute at application setup.

This project now needs to be installed. 

A setup.py is already provided in project’s base directory. 

Project dependencies get installed when this script is executed.

Python setup.py develop

By default, following dependencies are installed at the time of project set up −

Beaker

Genshi

zope.sqlalchemy

sqlalchemy

alembic

repoze.who

tw2.forms

tgext.admin ≥ 0.6.1

WebHelpers2

babel

After installation, start serving the project on development server by issuing following command in shell −

Gearbox serve -–reload -–debug

This sample application gives a brief introduction about TurboGears framework itself.

Thank you for reading till the end.

Peace out, 

Bek 
