---
layout: post
title: Sample blog post to learn markdown tips
subtitle: There's lots to learn!
gh-repo: daattali/beautiful-jekyll
gh-badge: [star, fork, follow]
tags: [tutorial]
comments: true
author: Bill Smith (edited by Mohammad Abaeiani)
categories: Tutorial
---

{: .box-success}
This is a demo post to show you how to write blog posts with markdown.  I strongly encourage you to [take 5 minutes to learn how to write in markdown](https://markdowntutorial.com/) - it'll teach you how to transform regular text into bold/italics/tables/etc.<br/>I also encourage you to look at the [code that created this post](https://raw.githubusercontent.com/daattali/beautiful-jekyll/master/_posts/2020-02-28-sample-markdown.md) to learn some more advanced tips about using markdown in Beautiful Jekyll.

**Here is some bold text**

## Here is a secondary heading

[This is a link to a different site](https://deanattali.com/) and [this is a link to a section inside this page](#local-urls).

Here's a table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |

How about a yummy crepe?

![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg)

It can also be centered!

![Crepe](https://beautifuljekyll.com/assets/img/crepe.jpg){: .mx-auto.d-block :}

Here's a code chunk:

~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.

## Local URLs in project sites {#local-urls}

When hosting a *project site* on GitHub Pages (for example, `https://USERNAME.github.io/MyProject`), URLs that begin with `/` and refer to local files may not work correctly due to how the root URL (`/`) is interpreted by GitHub Pages. You can read more about it [in the FAQ](https://beautifuljekyll.com/faq/#links-in-project-page). To demonstrate the issue, the following local image will be broken **if your site is a project site:**

![Crepe](/assets/img/crepe.jpg)

If the above image is broken, then you'll need to follow the instructions [in the FAQ](https://beautifuljekyll.com/faq/#links-in-project-page). Here is proof that it can be fixed:

![Crepe]({{ '/assets/img/crepe.jpg' | relative_url }})


## Markdown cheat sheet

|Element|Syntax|
|---|---|
|[Headlines](https://tutorialmarkdown.com/sintaxis/#encabezados)|# H1<br>## H2<br>## H3|
|[Boldface](https://tutorialmarkdown.com/sintaxis#negrita)|`**texto en negrita**`<br>`__texto en negrita__`|
|[Italics](https://tutorialmarkdown.com/sintaxis#cursiva)|`*texto en cursiva*`<br>`_texto en cursiva_`|
|[Dating](https://tutorialmarkdown.com/sintaxis#citas)|> cita|
|[Sorted Lists](https://tutorialmarkdown.com/sintaxis#listas-ordenadas)|1. Primer elemento<br>1. Segundo elemento|
|[Unordered lists](https://tutorialmarkdown.com/sintaxis#listas-no-ordenadas)|* Primer elemento<br>* Segundo elemento<br> <br>+ Primer elemento<br>+ Segundo elemento<br> <br>- Primer elemento<br>- Segundo elemento|
|[Code](https://tutorialmarkdown.com/sintaxis#codigo)|`código`|
|[Horizontal line](https://tutorialmarkdown.com/sintaxis#lineas-horizontales)|---|
|[Links](https://tutorialmarkdown.com/sintaxis#enlaces)|[anchor](https://enlace.tld "título")|
|[Imagery](https://tutorialmarkdown.com/sintaxis#imagenes)|![Alt](/ruta/imagen.png)|
|[Stalemate](https://tutorialmarkdown.com/sintaxis-extendida#tablas)|\| Color \| Código \|<br>\| ----------- \| ----------- \|<br>\| Rojo \| #FF0000 \|<br>\| Azul \| #0000FF \||
|[Advanced Code Blocks](https://tutorialmarkdown.com/sintaxis-extendida#bloques-de-codigo)|```<br>{<br>  "Nombre": "Edu",<br>  "Peso": "72Kg"<br>}<br>```|
|[Syntax highlighting](https://tutorialmarkdown.com/sintaxis-extendida#resaltado-de-sintaxis)|```json<br>{<br>  "Nombre": "Edu",<br>  "Peso": "72Kg"<br>}<br>```|
|[Footnotes](https://tutorialmarkdown.com/sintaxis-extendida#notas-al-pie)|Texto con referencia. [^1]<br> <br>[^1]: Nota de la referencia|
|[Header IDs](https://tutorialmarkdown.com/sintaxis-extendida#ids-de-cabecera)|## Encabezado {#id-personalizado}|
|[Lists of definitions](https://tutorialmarkdown.com/sintaxis-extendida#listas-de-definiciones)|Término<br>: definición|
|[Strikethrough text](https://tutorialmarkdown.com/sintaxis-extendida#texto-tachado)|`~~Texto tachado~~`|
|[To-do lists](https://tutorialmarkdown.com/sintaxis-extendida#listas-de-tareas)|- [x] Primera tarea<br>- [ ] Segunda tarea<br>- [ ] Tercera tarea|
|[Emojis (copy and paste)](https://tutorialmarkdown.com/sintaxis-extendida#copiar-y-pegar-emojis)|😄|
|[Emojis (shortcodes)](https://tutorialmarkdown.com/sintaxis-extendida#shortcodes-de-emojis)|:smile:|
|[Automatic Links](https://tutorialmarkdown.com/sintaxis-extendida#enlaces-automaticos)|https://www.neoguias.com|
|[Disable auto-links](https://tutorialmarkdown.com/sintaxis-extendida#enlaces-automaticos)|`https://www.neoguias.com`|