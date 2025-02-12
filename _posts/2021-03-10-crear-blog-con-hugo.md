---
title: "Generar una página web estática con Hugo"

# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_autogeneratedsamplecontent_9

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Maria Soria
# multiple category is not supported
category: auto generated
# multiple tag entries are possible
tags: [hugo, website]
# thumbnail image for post
img: ":hugo.png"
# disable comments on this page
comments_disable: true

# publish date
date: 2021-03-10 16:28:34 +06:00

# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file

---

Crea una web site o un blog con un generador estático siguiendo los siguientes pasos.

Antes de empezar sitúate en el directorio en el que quieres generar el proyecto.

1. Si no tienes instalado Hugo, puedes hacerlo a través de homebrew escribiendo lo siguiente en tu terminal:

    `brew install hugo`

   (si lo tenías instalado, ve directamente el punto 2)

2. A continuación, genera una nueva website de Hugo:

    `hugo new site <nombre>`

3. Ir al directorio que ya se ha creado y crear un repositorio de git:

   ```cd <nombre>```

   ```git init```

5. Añade como submódulo de git el [tema](https://themes.gohugo.io/) que hayas elegido para tu website. En mi caso será "kross":

    `git submodule add <url-del-repositorio-git-del-tema> themes/<nombre-tema>`

6. Abre el proyecto con tu IDE favorito. Verás que en tu árbol de proyecto tienes varias carpetas creadas por defecto (archetypes, content, data...).
   Estas carpetas serán donde iremos poniendo cada una de las partes de nuestra web site. Estas partes ya las tenemos incluidas,
   solo que no están donde deberían.

   ![root del proyecto](:/hugo/root.png "root del proyecto")

7. Ve a */themes/\<nombre-tema>/exampleSite*. Esta carpeta contiene exactamente lo que necesitamos, así que ahora procederemos a copiar el contenido de
   cada una de sus subcarpetas en la homónima. Esto es que, por ejemplo, el contenido de */themes/\<nombre-tema>/exampleSite/content* tendremos
   que copiarlo dentro de la carpeta **content** que hay en la raíz del proyecto. Y lo mismo con **data** y **static**.

   ![subcarpetas del proyecto](:/hugo/move.png "subcarpetas")

8. También tendremos que copiar el fichero de configuración (*config.toml*) y ponerlo en la raíz de nuestro proyecto.

   ![fichero config del proyecto](:hugo/config.png "config.toml")

9. Una vez hecho esto ya podemos hacer el "build" del proyecto. Para ello deberemos escribir en la terminal (desde nuestro root):

   `hugo serve`

    El proyecto comenzará a compilar y aparecerá lo siguiente en la terminal:

   ```Serving pages from memory```
   ```Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender```
   ```Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)```
   ```Press Ctrl+C to stop```

10. Ya podremos ver nuestra página web desde el navegador en la url:

     `http://localhost:1313/`

11. A partir de aquí, sólo nos queda realizar las modificaciones necesarias a los ficheros *.md* o *.yml* que encontraremos
dentro de las carpetas **content** y **data** de nuestra raíz del proyecto para personalizar la web site a nuestro gusto.
Y también podremos personalizar la configuración de nuestra web site a través del fichero *config.toml*.

      ![personalizacion del proyecto](:hugo/modif.png "personalizacion")
