# Práctica 1 — Reflexión

Cada integrante firma al menos una respuesta. Las respuestas son un borrador: cada quien debe revisar, ajustar con sus propias palabras y firmar la suya.

## 1\. ¿Qué ventajas tiene que el historial de Git sea la bitácora del proyecto, en comparación con enviar archivos por correo o WhatsApp?

Con Git cada cambio queda registrado con **quién lo hizo, cuándo y por qué** (el mensaje del commit), y no se pierde nada: siempre se puede volver a una versión anterior. Por correo o WhatsApp terminamos con archivos como `final\_v2\_ahora\_si.docx`, sin saber cuál es el bueno ni quién cambió qué. Además, en Git todos trabajan sobre la misma copia central: las ramas permiten avanzar en paralelo sin pisarse el trabajo, y el Pull Request obliga a que alguien revise antes de integrar. Para el profesor, los commits son evidencia objetiva de la participación de cada integrante.

— *Jehyson (Líder)*

## 2\. ¿Qué información les hizo falta para formular su hipótesis y a quién se la pedirían en un proyecto real?

Nos faltó saber **cuál de los tres archivos `.sql` es el vigente**, si el sistema llegó a usarse en producción y con cuántos usuarios, qué **versión de PHP** y de servidor requiere, cómo se instala y qué partes del proceso de residencia cubre realmente. También nos faltó saber si los documentos PDF del repositorio son reales o de prueba. En un proyecto real se lo pediríamos al **desarrollador original** (si se le puede contactar), al **departamento que usaba el sistema** (División de Estudios Profesionales o Gestión Tecnológica y Vinculación) y al **área de sistemas** que lo tenía instalado.

— *Myrka (QA / Documentador)*

## 3\. ¿Por qué conviene trabajar en un fork y no directamente en el repositorio original?

Porque **no tenemos permiso** para modificar el repositorio del autor, y aunque lo tuviéramos, no sería correcto cambiar su trabajo. El fork es **nuestra copia controlada**: podemos crear ramas, documentar y experimentar sin afectar el original, y conservamos todo su historial de commits, que necesitaremos en la Práctica 6. Además, cada equipo tiene su propio fork, así que los análisis de los Equipos A y B se mantienen independientes y después se pueden comparar.

— *Jose Guadalupe (Analista)*

