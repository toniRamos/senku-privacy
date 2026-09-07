# Marble Solitaire &ndash; Privacy Policy

Static privacy policy page for the **Marble Solitaire** mobile game, published with GitHub Pages.

## Public URL

**https://toniramos.github.io/senku-privacy/**

Es la URL que se pega en Play Console (*App content &rarr; Privacy policy*) y en la ficha.

🚨 **El repo es PÚBLICO a propósito, al contrario que el del juego.** Play exige que la política
sea accesible sin autenticación: si el repo fuera privado, la URL daría 404 y **la revisión de la
ficha se rechaza**.

## Ficheros

| Fichero | Para qué |
|---|---|
| `index.html` | La política entera, HTML autocontenido con CSS en línea. Sin dependencias externas |
| `.nojekyll` | Que Pages sirva los ficheros tal cual y se salte el build de Jekyll |

## Actualizar la política

Editar `index.html`, **subir la `Effective Date`**, y:

```bash
git add index.html && git commit -m "Update privacy policy" && git push
```

Pages redespliega solo en cada push a `main`. Tarda ~1 minuto.

## ⚠️ La política tiene que describir lo que la app hace de verdad

Este texto declara anuncios de AdMob y analítica de Firebase. **Si el juego se publica sin una de
las dos, la política sobredeclara** y hay que quitar esa sección. Y al revés es peor: añadir una
librería que recoja datos sin actualizar esto es lo que hace que Play retire una app.

El sitio de verificarlo es la fase de política del `PLAN.md` del juego, que cruza las secciones de
aquí con los autoloads que el juego tiene cableados de verdad.
