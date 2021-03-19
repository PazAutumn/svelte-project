<script>
  import { link } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";
</script>

<div class="write">
  <h3>Write less code</h3>
  <h5>
    Svelte construye componentes libres de boilerplate usando lenguajes que ya
    conoces - HTML, CSS Y Javascript.
  </h5>
  <p>
    Reducir la cantidad de código que tiene que escribir es un objetivo
    explícito de Svelte. Para ilustrar, veamos un componente muy simple
    implementado en React, Vue y Svelte. Primero, la versión Svelte:
  </p>
  <CodeBox title={"svelte"} src={"/assets/img/svelte-example1.png"} />
  <p>¿Cómo construiríamos esto en React? Probablemente se vería así:</p>
  <CodeBox title={"react"} src={"/assets/img/react-example1.png"} />
  <p>Aquí hay un componente equivalente en Vue:</p>
  <CodeBox title={"vue"} src={"/assets/img/vue-example1.png"} />
  <p>
    En otras palabras, se necesitan 442 caracteres en React y 263 caracteres en
    Vue, para lograr algo que requiere 145 caracteres en Svelte. ¡La versión
    React es literalmente tres veces más grande! Un componente React es
    típicamente alrededor de 40% más grande que su equivalente en Svelte.
  </p>
  <div class="source">
    <a href="https://svelte.dev/blog/write-less-code" target="_blank" use:link>
      Fuente
    </a>
  </div>
</div>

<style type="text/scss">
  p {
    font-size: 18px;
    font-weight: 200;
  }
  h3 {
    text-align: center;
    font-weight: 300;
  }
</style>
