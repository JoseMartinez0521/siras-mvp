# Análisis del sistema heredado — Equipo \[B]

**Materia:** Gestión de Desarrollo de Proyectos de Software · TecNM, Instituto Tecnológico de Matehuala
**Periodo:** Agosto – Diciembre 2026
**Sistema analizado:** Sistema de Control Escolar de Servicio Social y Residencia Profesional
**Repositorio base:** https://github.com/cbarreral/Sistema\_de\_Control\_Escolar\_de\_Servicio\_Social\_y\_Residencia\_Profesional

## Integrantes y roles (Práctica 1)

|Integrante|Nombre|Usuario de GitHub|Rol en la Práctica 1|
|-|-|-|-|
|1|Jehyson|@JehysonMJ|Líder de proyecto|
|2|Jose Guadalupe|@JoseMartinez0521|Analista|
|3|Myrka|@MyrkaSalazar04|QA / Documentador|

## Hipótesis inicial

> Escrita en la Práctica 1 sin abrir el código, solo observando los nombres de carpetas y archivos del repositorio. Se conserva sin cambios para compararla con los hallazgos reales en la Práctica 9.

### ¿Qué creemos que hace el sistema?

Creemos que es un sistema web para llevar el control de los trámites de **Residencia Profesional** y **Servicio Social** de un Instituto Tecnológico. El nombre del repositorio lo indica, y lo confirman varias carpetas: `Kardex`, `IMSS` y `Servicio` (con archivos como `\*\_CartaLiberacion.pdf`) parecen guardar los documentos que el alumno debe entregar para iniciar su residencia: su kárdex, su comprobante de afiliación al IMSS y su carta de liberación del servicio social. La carpeta `Documentos` tiene PDF con prefijos `Doc\_\_` y `Rep\_\_` seguidos de una fecha, por lo que suponemos que el alumno sube documentos y **reportes** periódicos durante la residencia.

En `Documentacion` aparecen el formato oficial `P-DRSS-02-F-06\_Solicitud\_de\_Residencia\_Profesional`, un calendario de residencias y una lista de empresas vinculadas. Por eso pensamos que el sistema digitaliza la **solicitud de residencia** y lleva un **catálogo de empresas**. Los nombres de las vistas (`Vistas/modulos`) refuerzan esta idea: `solicitudRecidencia`, `solicitudes`, `visitas`, `evaluaciones`, `calificaciones`, `constancia-alumno`, `carreras`, `materias` y `usuarios`.

### ¿Para quién?

Para varios tipos de usuario. En `Vistas/modulos` hay cinco menús distintos (`menu`, `menuAlumno`, `menuAcademico`, `menuIndustrial` y `menuJefe`), por lo que suponemos cinco roles: un **administrador**, el **alumno** residente, el **asesor académico** (profesor del Tecnológico), el **asesor industrial** (de la empresa) y el **jefe de división o de carrera**.

### ¿Con qué tecnología?

* **PHP** en el servidor: `index.php` en la raíz y carpetas `Controladores` y `Modelos` con archivos `.php`. La separación en `Modelos`, `Vistas` y `Controladores` sugiere el patrón **MVC**, aparentemente sin un framework (no vemos `composer.json`, `vendor/` ni carpetas típicas de Laravel o CodeIgniter).
* **MySQL/MariaDB** como base de datos: hay tres respaldos `sistemacontrolescolar\*.sql` en la raíz.
* **Apache**: el archivo `.htaccess` hace pensar en direcciones "amigables" que pasan todas por `index.php`.
* **Librerías de terceros**: `tcpdf` (generar PDF, quizá constancias), `PHPMailer` (enviar correos), `impExcel`, `expExcel` e `ImportarExcel` (importar y exportar Excel; hay un `importarUser.xls` para cargar usuarios de forma masiva) y `Vistas/bower\_components` (paquetes de interfaz como jQuery y Bootstrap, instalados con Bower).
* La carpeta `Ajax` sugiere que algunas pantallas se actualizan sin recargar la página.

### ¿Qué tan grande es?

El repositorio tiene alrededor de **8,400 archivos y \~100 MB**, pero creemos que **la gran mayoría no es código escrito por el desarrollador**:

|Carpeta|Archivos aprox.|Lo que suponemos|
|-|-:|-|
|`Vistas`|\~7,000|Casi todo es `bower\_components` (librerías de interfaz); lo propio serían `modulos` (49 vistas) y `plantilla.php`|
|`Modelos`|\~260|Pocos modelos propios; el resto parece una librería de Excel|
|`impExcel`|\~230|Librería de Excel|
|`tcpdf`|\~110|Librería de PDF|
|`Controladores`|19|Código propio|
|`Documentos`, `IMSS`, `Kardex`, `Servicio`, `Documentacion`|\~30 PDF/DOCX|Documentos subidos, no código|

Estimamos que el código propio está entre **5,000 y 15,000 líneas** (menos del 5% de los archivos), por lo que lo vemos como un sistema **pequeño a mediano**, desarrollado probablemente por **una sola persona** (el repositorio pertenece a un usuario individual) alrededor de **2021**, según las fechas de los archivos.

### Primeras preocupaciones

* Hay documentos que parecen **personales** (kárdex, IMSS, cartas de liberación, CV) subidos al repositorio público.
* Tres archivos `.sql` distintos: no sabemos cuál es el vigente.
* No vemos README técnico, manual de instalación, licencia ni pruebas.

## Índice de entregables

|Práctica|Carpeta|
|-|-|
|1. Arranque del proyecto y control de versiones|[practica-01](practica-01/)|



