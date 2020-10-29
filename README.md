# Presentación Modelos Estocásticos

Escrita en Markdown y LaTex Beamer y transpilada con pandoc.

## Requisitos

1. LaTex
2. pandoc

## Generar PDF

```
pandoc pre.md -t beamer -o pre.pdf
```

Si se quisiera generar el código LaTex para complementarlo aún más en un editor de LaTex propio se puede usar el siguiente comando: 

```
pandoc pre.md -t beamer -o pre.tex
```

## Consideraciones

### Cambiar Temas

En el preambulo de la presentación se introducen los metadatos de esta.

Manipulando las siguientes etiquetas se pueden probar distintas combinaciones de temas:

```
theme:
- PaloAlto
colortheme:
- dolphin
```

Se puede visualizar distintas combinaciones [aquí](https://mpetroff.net/files/beamer-theme-matrix/).

Al igual que los temas, otra información importante se puede modificar en el mismo preambulo.

### Jerarquia de Secciones

1 solo bang crea nuevas secciones (introduce un elemento en la tabla de contenido y crea una diapositiva antes del contenido de la sección.

2 bang indica una nueva diapositiva.

3 bang indican recuadros o subsecciones dentro de una diapositiva.

```
# Sección 1

## Diapositiva 1

Hola 1

### Ecuaciones Importantes

1. Esto estara dentro de un recuadro
2. $x = y$
3. $\pi = 3.1415...$

### Otro recuadro
Me gusta Markdown

## Diapositiva 2

Hola 2
```

### Listas Incrementales

Para crear listas incrementales se utiliza el siguiente syntax:

```
::: incremental
1. ¿Hola
2. Cómo 
3. Estan?
:::
```

Es decir, el PDF tendra páginas consecutivas donde van apareciendo cada uno de los elementos de las listas.

### Imagenes

La imagen debe estar en la misma carpeta o en un subdirectorio.

Se pueden introducir de la siguiente manera:

```
\begin{figure}
\centering
\includegraphics[width=4cm]{img_1.png}
\end{figure}
```

Si se introducen con el syntax usual de Markdown no se puede controlar el tamaño de la imagen.

### Videos

El video debe estar en la misma carpeta o en un subdirectorio. Esto acepta varios formatos, sin embargo es recomendable usar mp4. (Si se tiene un GIF convertirlo a mp4).

Se puede introducir de la siguiente manera:

```
\centering
\includemedia[
  width=0.4\linewidth,
  totalheight=0.225\linewidth,
  activate=pageopen,
  passcontext,  %show VPlayer's right-click menu
  addresource=seq2seq_1.mp4,
  flashvars={
    %important: same path as in `addresource'
    source=seq2seq_1.mp4
    &autoPlay=true
    &loop=true
  }
]{\fbox{Click!}}{VPlayer.swf}
```

Lo importante es cambiar `addresource` y `source`.

### Ecuaciones

Para introducir terminos matemáticos se rodean por el simbolo peso `$`.

Por ejemplo `$x^4`.

Para introducir una ecuación (automáticamente son enumeradas y centradas) se rodea la ecuación con dos simbolos pesos, por ejemplo:

`$$x = y + 2$$`
