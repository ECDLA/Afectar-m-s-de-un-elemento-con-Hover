<h1>Afectar dos elementos al pasar él mouse por uno con CSS puro</h1>

<h2>INTRODUCCIÓN</h2>
Te podrás dar cuenta que al usar la pseudo clase «:hover», al pasar él puntero esté hace la acción indicada -para ejemplos prácticos usaremos la propiedad «opacity»- como cambiar la opacidad a un elemento pero, ¿qué pasa si se quiere afectar a dos elementos a la vez con la pseudo clase «hover»? Esto se complica aún más si vas empezando.
En este post te mostraré cómo solucionar este inconveniente y si tienes alguna otra solución no dudes en comentarlo para poder ayudar a otros.

<h2>SOLUCIÓN</h2>
Si entiendes esto no leas lo demás, lo siguiente es un ejemplo práctico.
En la clase padre de los elementos declara una variable:

<code>.video__miniatura {
    . . .
    /* Variable inical */
    --icon-video--opacidad: 1;
}</code>

y en él hover del padre modifica la variable para darle él valor deseado.

<code>.video__miniatura:hover {
    /* Variable modificada */
    --icon-video--opacidad: 0.5;
}</code>

Y al segundo objeto darle la variable a modificar.

<code>.video__icon-video {
    . . .
    /* Variable modificable */
    opacity: var(--icon-video--opacidad);
}</code>

<h2>¿QUÉ TEMAS SE TOCARAN?</h2>
Clases*
Variables
Pseudoelementos
Before*
Hover
* Estos elementos no son necesarios para la solución.

<h2>PROBLEMA A SOLUCIONAR</h2>
Queremos poner una imagen que por enfrente tenga un pseudo elemento con degradado radial él cual arriba será transparente y debajo una transparencia del 40% y enfrente tenemos un icono de video centrado.
Lo que se quiere hacer es aplicarle una opacidad 0 al fondo degradado y al icono darle una opacidad del 50%, esto al momento que él cursor pase por encima de la imagen.

<h2>SOLUCIÓN AL PROBLEMA</h2>
Primero se tiene que encerrar a los objetos a quienes se les quiere afectar con él hover, en este caso dentro estarán la imagen del video y él icono él cual quería algo así nuestro código.

<pre><body>
    <main class="principal">
        <div class="video">
            <figure class="video__miniatura">
                <img src="IMG/megu-guapo.png" alt="miniatura video" class="video__imagen">
                <img src="IMG/Trazado 21.svg" alt="icono de video" class="video__icon-video">
            </figure>
        </div>
    </main>
</body></pre>

Para la solución solo usaremos las clases: video__miniatura y video__icon-video por lo que lo demás lo pueden ignorar.
Empezaremos con él CSS él cual le aplicaremos una variable la cual se modificará para afectar al otro elemento por lo que sería quedaría algo así:

<code>.video__miniatura {
    . . .
    /* Variable inical */
    --icon-video--opacidad: 1;
}</code>

Y en la segunda clase a la cual queremos modificar, su CSS quedaría así:

<code>.video__icon-video {
    . . .
    /* Variable modificable */
    opacity: var(--icon-video--opacidad);
}</code>

Ahora en él hover es tan fácil modificar él valor de la variable a la deseada.

<code>.video__miniatura:hover {
    /* Variable modificada */
    --icon-video--opacidad: 0.5;
}</code>

Tan fácil como eso.
