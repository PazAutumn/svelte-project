<script>
  import { Router, link, navigate } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";

  const goNext = () => {
    navigate('/essentials')
  }
</script>

<h1>Routing</h1>
<p>
  La opciones más populares para implementar el routing 
  en svelte son 
  <a href="https://sapper.svelte.dev/" target="_blank" use:link>Sapper</a>, 
  <a href="https://www.npmjs.com/package/svelte-spa-router" target="_blank" use:link>svelte-spa-router</a> y
  <a href="https://www.npmjs.com/package/svelte-routing" target="_blank" use:link>svelte-routing</a> que 
  será el que usaremos en nuestro proyecto ya que es una de las librerías con más descargas semanales en npm.
</p>
<p>Para instalarlo en ejecutaremos el siguiente script en la carpeta raíz de nuestro proyecto</p>
<CodeBox title={'terminal'}>
  &dollar; npm install --save svelte-routing
</CodeBox>
<h5>Usage</h5>
<CodeBox title={'terminal'} src="/assets/img/routing-example1.png"/>
<p>Ahora echemos un vistazo en el código.</p>
<Router>
  <!--ul>
    <li>Usando anchor: <a href="/blog" use:link>Blog</a></li>
    <li>Usando Link: <Link to="/blog">Blog</Link></li>
  </ul-->
</Router>
<button class="btn waves-effect waves-light" name="action" on:click={goNext}>Siguiente
  <i class="material-icons right">send</i>
</button>