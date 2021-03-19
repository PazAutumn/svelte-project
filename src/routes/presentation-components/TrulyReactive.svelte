<script>
  import { link } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";

  const compileText = `<strong>COMPILE STEP</strong>`;
</script>

<div class="truly">
  <h3>Truly reactive</h3>
  <h5>
    No más complejas librerias de manejos de estado - Svelte aporta reactividad
    al Javascript en si mismo.
  </h5>
  <br />
  <div class="video">
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/AdNJ3fydeao"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    />
  </div>
  <p>
    En el antiguo Svelte, le dirías a la computadora que algún estado había
    cambiado llamando al método this.set:
  </p>
  <CodeBox title={"svelte 2"} src={"/assets/img/svelte-example3.png"} />
  <p>
    Eso haría que el componente "reaccionara". Hablando de eso, this.set es casi
    idéntico al método this.setState utilizado en los clásicos (pre-hooks)
    React:
  </p>
  <CodeBox title={"react"} src={"/assets/img/react-example3.png"} />
  <p>
    Hay algunas diferencias técnicas importantes (React no es reactivo) pero
    conceptualmente es lo mismo.
  </p>
  <p>
    Svelte simplifica los cambios de estados llevandolos a una simple
    asignación.
  </p>
  <CodeBox title={"svelte 3"} src={"/assets/img/svelte-example4.png"} />
  <p>
    Es decir el estado está inferido, cada vez que se le asigna un nuevo valor a
    una prop o variable Svelte lo interpreta como un cambio de estado y ejecuta
    un {@html compileText} osea se vuelve a renderizar. Mientras en React es mucho
    más ruidoso, expresa exactamente el mismo concepto pero con más del 60% más de
    caracteres. Mientras uno lee el código, tiene que hacer mucho más trabajo para
    comprender la intención del autor.
  </p>
  <div class="source">
    <a
      href="https://svelte.dev/blog/svelte-3-rethinking-reactivity"
      target="_blank"
      use:link
    >
      Fuente
    </a>
  </div>
</div>

<style type="text/scss">
  p {
    font-size: 18px;
    font-weight: 200;
  }
  h3,
  h5 {
    text-align: center;
    font-weight: 300;
  }
  .video {
    display: flex;
    justify-content: center;
  }
</style>
