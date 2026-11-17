# Proyecto Júpiter

Asistente de marketing para videojuegos desarrollado como proyecto de PontIA. El MVP usa **Possessed Kingdom** para probar si podemos reducir el trabajo manual del flujo de PK Marketing y mantener la calidad de la selección y del contacto.

## Alcance del MVP

**Crear campaña → descubrir creadores → seleccionar con fuentes → preparar el contacto → revisar y enviar → gestionar respuestas → registrar el resultado.**

- Una campaña, un operador, YouTube como fuente y un buzón de Gmail. Hasta diez candidatos por lote.
- Cada candidato seleccionado tiene fuentes verificables. La aplicación prepara el correo y registra el estado del contacto.
- El operador aprueba cada envío y cada respuesta. Las respuestas salen en el hilo original y el sistema evita envíos duplicados.

Para después quedan otras fuentes y buzones, agentes autónomos, RAG de propósito general y analítica de cobertura.

## Herramientas

| Parte del flujo | Herramientas |
| --- | --- |
| Aplicación web y campaña | Python, FastAPI y Jinja |
| Descubrimiento y selección | YouTube Data API, PostgreSQL con pgvector y embeddings de Gemini para recuperar evidencias |
| Borradores de contacto y respuesta | Gemini, con fuentes y una plantilla revisada |
| Envío y gestión de hilos | Gmail API con OAuth |
| Desarrollo y despliegue | Docker Compose en local, Docker y GitHub Actions. Proveedor cloud por acordar entre AWS y Azure |

## Organización y documentación

- **Miro** para definir el alcance, recorrer los diagramas y comentar la propuesta. Tras acordar el diseño, trasladaremos las decisiones y tareas a GitHub. [Tablero de Júpiter](https://miro.com/app/board/uXjVEMnlj6o=/?moveToWidget=3458764690740935105)
- **GitHub Issues y Projects** para concretar tareas, asignar responsables y seguir el trabajo. Usaremos pull requests para revisar cambios. [Issues](https://github.com/joseppi/proyecto-jupiter/issues) · [Projects](https://github.com/joseppi/proyecto-jupiter/projects)
- **GitHub Wiki** para la guía de incorporación, el glosario y los acuerdos de trabajo. [Wiki](https://github.com/joseppi/proyecto-jupiter/wiki)
- **Documentación versionada en `docs/`** para la arquitectura, el modelo de datos, la configuración, el despliegue y la guía de demo. Se actualizará junto con el código.
- **GitHub Actions** para ejecutar pruebas unitarias y de integración en cada pull request, construir las imágenes Docker y desplegar la versión aprobada. Las pruebas automáticas usarán servicios simulados cuando impliquen envíos. [Actions](https://github.com/joseppi/proyecto-jupiter/actions)

## Cómo validaremos el MVP

Haremos el recorrido completo con un buzón de prueba. Sobre el mismo lote, compararemos Júpiter con el flujo actual de PK Marketing por tiempo hasta tener un borrador revisado, perfiles relevantes con fuentes y correcciones necesarias. También compararemos la búsqueda vectorial con una búsqueda por palabras clave.

**Estado** · Propuesta de MVP e implementación pendiente.
