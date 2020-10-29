# Presentación Modelos Estocásticos

Escrita en Markdown y LaTex Beamer y transpilada con pandoc.

## Requisitos

1. LaTex
2. pandoc

## Generar PDF

```
pandoc pre.md -t beamer -o pre.pdf
```

## Consideraciones

### Jerarquia de Secciones

1 solo bang crea nuevas secciones (introduce un elemento en la tabla de contenido y crea una diapositiva antes del contenido de la sección.

2 bang indica una nueva diapositiva.

3 bang indican recuadros o subsecciones dentro de una diapositiva.

```
# Sección 1

## Diapositiva 1

Hola 1

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

El video debe estar en la misma carpeta o en un subdirectorio.

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
