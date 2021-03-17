<script>
  import { Link } from "svelte-routing";

  const title = "Hello Frogmis";
</script>

<h1>{title}</h1>
<h5>Welcome to the svelte workshop</h5>
<p>
  Svelte es un nuevo enfoque radical para construir interfaces de usuario.
  Mientras que los marcos tradicionales como React y Vue realizan la mayor parte
  de su trabajo en el navegador, Svelte cambia ese trabajo a un “paso de
  compilación” que ocurre cuando se construye la aplicación. En lugar de
  utilizar técnicas como la diferenciación virtual del DOM, Svelte escribe
  código que actualiza quirúrgicamente el DOM cuando cambia el estado de su
  aplicación.
  <br />
  <br />
  Svelte se destaca por tres principales razones.
</p>
<Link to="write-less-code">
  <div class="box red">Write less code</div>
</Link>
<Link to="no-virtual-dom">
  <div class="box blue">No virtual DOM</div>
</Link>
<Link to="truly-reactive">
  <div class="box gray">Truly reactive</div>
</Link>

<style type="text/scss">
  .box {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50px;
    border-radius: 0.5em;
    margin: 5px 20px;
    color: #f1f1f3;
  }
  h1,
  h5 {
    text-align: center;
  }
  p {
    padding: 20px;
    text-align: justify;
    font-size: 18px;
    font-weight: 200;
  }
  :global(a), :global(a):hover {
    text-decoration: none;
  }
  .gray {
    background-color: #575766;
  }
</style>
