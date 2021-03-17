<script>
  import { Router, Link, Route, link } from "svelte-routing";
  
  const title = 'Hello Frogmis'
  export let location;
</script>

<div class="row">
  <Router>
    <div class="col s4 left-col">
      <h1>{title}</h1>
      <h5>Welcome to the svelte workshop</h5>
      <p>
        Svelte es un nuevo enfoque radical para construir interfaces de usuario. 
        Mientras que los marcos tradicionales como React y Vue realizan la mayor parte de su trabajo en el navegador, 
        Svelte cambia ese trabajo a un “paso de compilación” que ocurre cuando se construye la aplicación. 
        En lugar de utilizar técnicas como la diferenciación virtual del DOM, Svelte escribe código que actualiza quirúrgicamente el DOM cuando cambia el estado de su aplicación.
        <br>
        <br>
        Svelte se destaca por tres principales razones.
      </p>
      <Link to="write-less-code">
        <div class="box red">
          Write less code
        </div>
      </Link>
      <Link to="no-virtual-dom">
        <div class="box blue">
          No virtual DOM
        </div>
      </Link>
      <Link to="truly-reactive">
        <div class="box gray">
          Truly reactive
        </div>
      </Link>
    </div>
    <div class="col s8 right-col">
      {#if location.pathname === '/'}
        <div class="home">
          <img src={'/assets/img/svelte-logo-outline.svg'} alt="">
          <img src={'/assets/img/svelte-logotype.svg'} alt="svelte-logotype">
          <img src={'/assets/img/svelte-logo-outline.svg'} alt="">
        </div>
      {:else}
      <Route path="write-less-code">
        <div class="write">
          <h3>Write less code</h3>
          <p>
            Reducir la cantidad de código que tiene que escribir es un objetivo 
            explícito de Svelte. Para ilustrar, veamos un componente muy simple 
            implementado en React, Vue y Svelte. Primero, la versión Svelte:
          </p>
          <div class="box code white-code">
            <div class="framework">SVELTE</div>
            <img src={'/assets/img/svelte-example1.png'} alt="">
          </div>
          <p>
            ¿Cómo construiríamos esto en React? Probablemente se vería así:
          </p>
          <div class="box code white-code">
            <div class="framework">REACT</div>
            <img src={'/assets/img/react-example1.png'} alt="">
          </div>
          <p>
            Aquí hay un componente equivalente en Vue:
          </p>
          <div class="box code white-code">
            <div class="framework">VUE</div>
            <img src={'/assets/img/vue-example1.png'} alt="">
          </div>
          <p>
            En otras palabras, se necesitan 442 caracteres en React y 263 
            caracteres en Vue, para lograr algo que requiere 145 caracteres 
            en Svelte. ¡La versión React es literalmente tres veces más grande!
            Un componente React es típicamente alrededor de 40% más grande que 
            su equivalente en Svelte.
          </p>
          <div class="source">
            <a href="https://svelte.dev/blog/write-less-code" target="_blank" use:link>Fuente</a>
          </div>
        </div>
      </Route>
      <Route path="no-virtual-dom">
        <div class="virtual">
          <h3>No virtual DOM</h3>
          <p>
            I did something awesome today. Lorem ipsum dolor sit amet, consectetur 
            adipisicing elit. Repudiandae enim quasi animi, vero deleniti dignissimos 
            sapiente perspiciatis. Veniam, repellendus, maiores.
          </p>
        </div>
      </Route>
      <Route path="truly-reactive">
        <div class="truly">
          <h3>Truly reactive</h3>
          <p>
            I did something awesome today. Lorem ipsum dolor sit amet, consectetur 
            adipisicing elit. Repudiandae enim quasi animi, vero deleniti dignissimos 
            sapiente perspiciatis. Veniam, repellendus, maiores.
          </p>
        </div>
      </Route>
      {/if}
    </div>
  </Router>
</div>

<style type="text/scss">
  .row {
    font-family: 'Overpass', sans-serif;
    .left-col {
      position: fixed;
      overflow: auto;
      padding-top: 50px;
      top: 0;
      bottom: 0;
      height: 100%;
      background-color: #676778;
      color: #f1f1f3;
      .box {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 50px;
        border-radius: .5em;
        margin: 5px 20px;
        color: #f1f1f3;
      }
      h1, h5 {
        text-align: center;
      }
      p {
        padding: 20px;
        text-align: justify;
        font-size: 18px;
        font-weight: 200;
      }
      :global(a) {
        text-decoration: none;
      }
      .gray {
        background-color: #575766;
      }
    }
    .right-col {
      background-image: url('/assets/img/svelte-logo-outline.svg');
      background-size: 20px;
      float: right;
      padding: 40px;
      overflow: auto;
      padding-top: 50px;
      top: 0;
      bottom: 0;
      height: 100vh;
      color: #444444;
      .home {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
      }
      .write {
        .framework {
          color: #f6fafd;
          background-color: #575766;
          border-radius: .5em;
          padding: 5px;
          position: absolute;
          right: 0;
        }
        img {
          height: 100%;
        }
      }
      .code {
        font-family: 'Fira Mono', monospace;
        border-radius: .5em;
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
      h5 {
        font-weight: 300;
      }
      img {
        height: 55px;
      }
    }
  }
  
</style>
