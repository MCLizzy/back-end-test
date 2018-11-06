# Prueba Back End Sani Medical
---
**¿Qué se busca evaluar?**

Principalmente los siguientes aspectos:

* Conocimientos y habilidades para el desarrollo de aplicaciones web.
* Conocimiento de un lenguaje de programación adecuado para la construcción del Back End. Opciones: PHP, Javascript.
* Conocimientos del Lenguaje SQL o NoSQL. Conocimiento de un gestor de base de datos y sus particularidades. Opciones: MySQL, MongoDB.
* Familiaridad con Frameworks y plataformas de desarrollo Web. Opciones: Laravel, AdonisJs.

### IMPORTANTE
---

1. Se requiere de una cuenta de **GitHub** para realizar este ejercicio.
2. Se solicita crear la aplicación utilizando la tecnología Web de su elección.
3. Recomendamos emplear un máximo de **3 horas** y enviar todo lo que puedas.
4. **Antes de comenzar a programar:**
    - Realizar un `Fork` de este repositorio.
    - Clonar el fork a su máquina local.
    - Crear un branch en su **cuenta de GitHub** utilizando su nombre completo.
5. **Al finalizar**, existen 2 opciones para entregar su proyecto:
    * Realizar un `Commit` de su proyecto, **enviar un `Pull Request` al branch con su NOMBRE**, y notificar a la siguiente dirección de correo electrónico (developer@sanimedicaltourism.com).
 - Crear un archivo comprimido (.zip o .rar) de su proyecto y enviar a la siguiente dirección de correo electrónico (developer@sanimedicaltourism.com).

 ### EJERCICIO PRACTICO
---

**Objetivo:** Crear una aplicación, que permita a los usuarios autorizados la gestión de sus tareas: Consultar, Crear, Modificar y Borrar.

**Requerimientos generales**

1. La aplicación debe cumplir con los siguientes **requisitos funcionales:**
	- Autenticación y autorización de usuarios.
	- Gestión de usuarios.
	- Persistencia de los datos (tareas) en una base de datos tipo SQL.
	- Métodos que debe publicar el servicio: Consultar, Crear, Actualizar y Borrar Tareas.
	- Se debe almacenar como mínimo la siguiente información relacionada con las tareas de los usuarios:
		- Usuario que creó la tarea.
		- Descripción.
		- Estado de la tarea: Se encuentra finalizada (si | no).
		- Fecha de creación.
		- Fecha de vencimiento.

### Descripción de Métodos
---

Nombre: **"Consultar Tareas"**  
Método HTTP: **GET**  
Path: `/tasks`  

**Parámetros:** Los necesarios para que el usuario pueda consultar las tareas programadas por diversios criterios:  
	- Consultar todas las tareas asignadas al usuario autenticado.  
	- Consultar solo las tareas finalizadas, pendientes o ambas.  
	- Ordernar por fecha de vencimiento.  
**Respuesta:** Listado de tareas con las condiciones establecidas en los parámetros.  
**Pre-requisito:** Usuario autenticado.  


Nombre: **"Crear Tarea"**  
Método HTTP: **POST**  
Path: `/tasks`  

**Parámetros:** Los necesarios para almacenar la información de la tarea creada por el usuario.  
**Respuesta:** La tarea creada.  
**Pre-requisito:** Usuario autenticado.  


Nombre: **"Actualizar Tarea"**  
Método HTTP: **UPDATE**  
Path: `/tasks/:id`  

**Parámetros:** Recibir un objeto con la información que el usuario desea actualizar:  
	- Identificador de la tarea. *(Obligatorio)*  
	- Descripción. *(Opcional)*  
	- Fecha de vencimiento. *(Opcional)*  
	- Finalizada (si | no). *(Opcional)*  
**Respuesta:** La tarea actualizada.  
**Pre-requisito:** Usuario autenticado y usuario autorizado (Solo el usuario que ha creado la tarea la puede actualizar).  


Nombre: **"Borrar Tarea"**  
Método HTTP: **DELETE**  
Path: `/tasks/:id`  

**Parámetros:** Recibir información que le permita identificar la tarea que el usuario debe borrar.  
**Respuesta:** La tarea eliminada.  
**Pre-requisito:** Usuario autenticado y usuario autorizado (Solo el usuario que ha creado la tarea la puede borrar).  

