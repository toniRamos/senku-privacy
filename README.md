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

🚨 **Este `index.html` NO se edita aquí: se despliega.** La fuente es
`senku/docs/privacy-policy.html`, en el repo del juego, y es la que sus tests cruzan con los
autoloads que la app carga de verdad. Editar aquí y acordarse de llevarlo allí es cómo el texto y
el código se separan sin que nadie lo vea.

Editar la fuente, **subir su `Effective Date`** (y la constante `Privacy.EFFECTIVE_DATE`, que un
test exige que sean el mismo día), y desplegar:

```bash
cp ../../senku/docs/privacy-policy.html index.html
git add index.html && git commit -m "Update privacy policy" && git push
```

Pages redespliega solo en cada push a `main`. Tarda ~1 minuto.

## ⚠️ La política tiene que describir lo que la app hace de verdad

Este texto declara anuncios de AdMob y analítica de Firebase. **Si el juego se publica sin una de
las dos, la política sobredeclara** y hay que quitar esa sección. Y al revés es peor: añadir una
librería que recoja datos sin actualizar esto es lo que hace que Play retire una app.

Quien lo verifica es `senku/tests/test_politica_privacidad.gd`, que cruza los `<h2>` de este texto
con el bloque `[autoload]` del `project.godot` del juego **en las dos direcciones**: una sección
sin autoload detrás y un autoload sin sección delante ponen la suite en rojo.
