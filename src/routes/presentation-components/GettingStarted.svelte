<script>
  import { link, navigate } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";

  const goNext = () => {
    navigate('/routing')
  }
</script>

<div class="write">
  <h3>Getting started</h3>
  <p>
    Los requisistos para crear un nuevo proyecto en Svelte son:
  </p>
  <ul>
    <li><strong>Node >= 8</strong></li>
    <li><strong>npm 5.2 (esta versión incluye npx)</strong></li>
  </ul>
  <CodeBox title={'terminal'}>
    &num; Comenzaremos ejecutando el siguiente comando en nuestra terminal
    &dollar; npx degit sveltejs / template my-svelte-project
    &num; Luego nos posicionamos en el proyecto
    &dollar; cd my-svelte-proyect
    &num; Adicionalmente si queremos usar TypeScript ejecutamos:
    &dollar; node scripts / setupTypeScript.js
    &num; Finalmente instalamos las dependencias y compilamos
    &dollar; npm install
    &dollar; npm run dev
    &num; Y listo! estamos listos para internarnos en Svelte
  </CodeBox>
  <p>
    Lo que acabamos de hacer es básicamente clonar un repositorio template de 
    Svelte. La razón para usar degit, en lugar del típico git clone, 
    es porque así evitamos descargarnos todo el historial de git del 
    proyecto, con lo es mucho más rápido.
  </p>
  <strong>Dato: npx es un ejecutador de paquetes binarios de npm, 
    es decir, que ejecuta entre otras cosas, una CLI.
    Si usas npx no tendrás que instalar nunca más un paquete como 
    paquete global para poder ejecutarlo.
  </strong>
  <div class="source">
    <a href="https://svelte.dev/blog/the-easiest-way-to-get-started" target="_blank" use:link>
      Fuente
    </a>
  </div>
  <h5>Nuestro proyecto</h5>
  <p>
    Para facilitar las cosas nosotros clonaremos el proyecto 
    que contiene el código fuente de este sitio.
  </p>
  <CodeBox title={'terminal'}>
    &dollar; git clone https://github.com/PazAutumn/svelte-project.git
    &num; Nos posicionamos en el proyecto y nos cambiamos a la rama develop
    &dollar; cd svelte-project
    &dollar; git checkout develop
    &num; Instalamos las dependencias
    &dollar; npm install
    &num; Finalmente compilamos el proyecto
    &dollar; npm run dev
  </CodeBox>
  <p>
    Este proyecto utiliza el framework de CSS 
    <a href="https://materializecss.com/" use:link target="_blank">Materialize</a>.
  </p>
  <button class="btn waves-effect waves-light" name="action" on:click={goNext}>Siguiente
    <i class="material-icons right">send</i>
  </button>
</div>

<style type="text/scss">
  ul {
    padding: 10px 30px;
    li {
      list-style: circle !important;
    }
  }
</style>