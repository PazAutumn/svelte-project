<script>
  import { link } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";
</script>

<div class="virtual">
  <h3>No virtual DOM</h3>
  <h5>
    Svelte compila el código en un pequeño vainilla JS sin framework - la
    aplicación se inicia rápidamente y se mantiene rápida.
  </h5>
  <p>
    No utiliza virtual DOM para realizar cambios en la aplicación como React o
    Vue: Este paso se basa en compilar nuestros componentes cuando realizamos un
    cambio, quitándole el trabajo al navegador de estar guardando en memoria
    nuestro árbol de elementos para hacer una comparación de un cambio que se
    hizo y solo se encarga de renderizar.
  </p>
  <p>Veamos un ejemplo:</p>
  <CodeBox title={"react"} src={"/assets/img/react-example2.png"} />
  <p>
    Observemos la función HelloMessage y supongamos que el prop name cambió de
    'mundo' a 'todos'.
  </p>
  <ul>
    <li>
      Ambas snapshots contienen un único elemento. En ambos casos es un DIV, lo
      que significa que podemos mantener el mismo nodo DOM.
    </li>
    <li>
      Enumeramos todos los atributos en el antiguo DIV y el nuevo para ver si es
      necesario cambiar, agregar o eliminar alguno. En ambos casos tenemos un
      atributo único: className un valor de "greeting".
    </li>
    <li>
      Al descender al elemento, vemos que el texto ha cambiado, por lo que
      tendremos que actualizar el DOM real.
    </li>
  </ul>
  <p>
    De estos tres pasos, solo el tercero tiene valor en este caso, ya que, como
    es el caso en la gran mayoría de las actualizaciones, la estructura básica
    de la aplicación no ha cambiado. Sería mucho más eficiente si pudiéramos
    saltar directamente al paso 3.
  </p>
  <CodeBox title={"svelte"} src={"/assets/img/svelte-example2.png"} />
  <p>
    (Este es casi exactamente el código de actualización que genera Svelte. A
    diferencia de los feameworks UI tradicionales, Svelte es un compilador que
    sabe en el build time cómo podrían cambiar las cosas en la aplicación, en
    lugar de esperar a hacer el trabajo en run time).
  </p>
  <h5>Entonces, ¿por qué los frameworks usan el DOM virtual?</h5>
  <p>
    Es importante comprender que el DOM virtual no es una característica. Es un
    medio para un fin, el fin es el desarrollo de UI declarativo e impulsado por
    el estado. El DOM virtual es valioso porque permite crear aplicaciones sin
    pensar en las transiciones de estado, con un rendimiento que generalmente es
    lo suficientemente bueno. Eso significa menos código con errores y más
    tiempo dedicado a tareas creativas en lugar de tediosas. Pero resulta que
    podemos lograr un modelo de programación similar sin usar DOM virtual, y ahí
    es donde entra en juego Svelte.
  </p>
  <div class="source">
    <a
      href="https://svelte.dev/blog/virtual-dom-is-pure-overhead"
      target="_blank"
      use:link
    >
      Fuente
    </a>
  </div>
</div>

<style type="text/scss">
  p,
  li {
    font-size: 18px;
    font-weight: 200;
  }
  h3,
  h5 {
    text-align: center;
    font-weight: 300;
  }
  ul {
    padding: 10px 30px;
    li {
      list-style: decimal !important;
    }
  }
</style>
