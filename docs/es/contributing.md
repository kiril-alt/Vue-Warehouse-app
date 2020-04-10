---
title: "Contribución"
description: "Pasos para facilitar el desarrollo y la depuración de Vue.js Warehouse."
permalink: /docs/vue-warehouse/contributing
created: "2018-03-29T10:57:00Z"
published: "2018-03-30T23:28:40.392224Z"
modified: "2019-06-05T12:51:34.314Z"
---

# Contribución

Asegúrese de leer esta **Guía de contribución** antes de hacer una contribución.

## Configuración de desarrollo

1. Haz un Fork y clona el repositorio
2. Ejecuta `npm install` para instalar dependencias
3. Ejecuta `npm test` para ejecutar la validación
4. Crea una rama para tu PR con `git checkout -b pr/your-branch-name`

### Scripts de NPM comúnmente utilizados

**Observa y sirve los ejemplos con recarga instántanea**
```shell
npm run start
```

**Verifica el formato del código**
```shell
npm run lint
```

**Ejecuta las pruebas unitarias**
```shell
npm run test
```

**Cree todos los archivos de distribución**
```shell
npm run build
```

## Guía para el Reporte de Problemas (Issues)

- La [lista de problemas (issues)][issues-link] de este proyecto es **exclusivamente** para informes de errores y solicitudes de funciones. Los problemas no conformes se cerrarán de inmediato.

- Intenta buscar tu problema, puede haber sido respondido o incluso corregido en la rama de desarrollo.

- Comprueba si el problema es reproducible con la última versión estable de Vue. Si estás utilizando una versión preliminar, indica la versión específica que estás utilizando.

- Es **obligatorio** que describas claramente los pasos necesarios para reproducir el problema que se está ejecutando. Los problemas que no tengan pasos de reprografía claros no serán evaluados. Si un problema etiquetado como "request-more-info" no recibe más información del autor del problema durante más de 5 días, se cerrará.

- Para los errores que involucran configuraciones de compilación, puede crear un repositorio de reproducción con pasos en el archivo README.

- Si tu problema está resuelto pero aún abierto, no dudes en cerrarlo. En caso de que encuentres una solución tu mismo, podría ser útil explicar cómo lo solucionaste.

## Guía para los "Pull Request"

- La rama `master` básicamente representa el estado de la última versión estable. Todo el desarrollo se debe hacer en ramas dedicadas. **No envíes PRs a la rama `master`.**

- Verifica un tópico de la rama relevante, p.ej. `develop`, y haz un merge hacia esa rama.

- Trabaja en las carpetas `src` y `nuxt` y **NO** registres la carpeta `dist` en los commits.

- Está bien tener múltiples commits pequeños mientras trabajas en el PR. Dejaremos que GitHub haga un squash automáticamente antes de un *merge*.

- Asegúrarte que pasen `npm run lint` y `npm run test`.

- Si agregas una nueva característica:
  - Agrega las pruebas que la acompaña.
  - Proporciona una razón convincente para agregar esta característica. Lo ideal sería que primero abrieras un tema de sugerencia y se validara antes de trabajar en él.

- Si corriges un error:
  - Proporciona una descripción detallada del error en el PR. Demo en vivo preferido.

[issues-link]: https://github.com/bazzite/vue-warehouse/issues
