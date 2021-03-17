<script>
  import { link } from "svelte-routing";
</script>

<div class="write">
  <h3>Write less code</h3>
  <p>
    Reducir la cantidad de código que tiene que escribir es un objetivo
    explícito de Svelte. Para ilustrar, veamos un componente muy simple
    implementado en React, Vue y Svelte. Primero, la versión Svelte:
  </p>
  <div class="box code white-code">
    <div class="framework">SVELTE</div>
    <img src={"/assets/img/svelte-example1.png"} alt="" />
  </div>
  <p>¿Cómo construiríamos esto en React? Probablemente se vería así:</p>
  <div class="box code white-code">
    <div class="framework">REACT</div>
    <img src={"/assets/img/react-example1.png"} alt="" />
  </div>
  <p>Aquí hay un componente equivalente en Vue:</p>
  <div class="box code white-code">
    <div class="framework">VUE</div>
    <img src={"/assets/img/vue-example1.png"} alt="" />
  </div>
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
  .write {
    .framework {
      color: #f6fafd;
      background-color: #575766;
      border-radius: 0.5em;
      padding: 5px;
      position: absolute;
      right: 0;
    }
    img {
      height: 100%;
    }
  }
  .code {
    font-family: "Fira Mono", monospace;
    border-radius: 0.5em;
    margin: 20px;
    display: flex;
    justify-content: left;
    position: relative;
    padding: 5px;
  }
  .white-code {
    background-color: #f6fafd;
  }
  .source {
    text-align: right;
  }
  p {
    font-size: 18px;
    font-weight: 200;
  }
  h3 {
    text-align: center;
    font-weight: 300;
  }
  img {
    height: 55px;
  }
</style>
