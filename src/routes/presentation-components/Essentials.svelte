<script>
  import { navigate } from "svelte-routing";
  import CodeBox from "../../components/CodeBox.svelte";

  let pokemon;

  const goNext = () => {
    navigate('/bonus-track')
  }

  let message = "";
  const sayHello = () => {
    message = "Hello!";
  }

  const getPokemon = async () => {
    pokemon = pokemon.toLowerCase();
    const res = await fetch(
      `https://pokeapi.co/api/v2/pokemon/${pokemon}/`
    );
    const data = res.json();
    if (res.ok) {
      return data;
    } else {
      throw new Error(data);
    }
  };
  let promise = getPokemon();

  const handleClick = () => {
    promise = getPokemon();
  }
</script>

<h1>Svelte essentials</h1>
<p>
  En mi experiencia con svelte estos features han sido los más útiles y que he
  usado con más frecuencia, ¡pero hay muchos más! sientete libre de explorar los
  <a href="https://svelte.dev/tutorial/basics" target="_blank">tutoriales</a> de svelte.
</p>
<h4>Adding data</h4>
<p>Manejar la data dinámicamente.</p>
<CodeBox>
  &num; Adding data 
  &lt;script&gt; 
    let name = 'Froggies'; 
  &lt;/script&gt;
  &lt;h1&gt;Hello &lcub;name.toUpperCase()&rcub;!&lt;/h1&gt;
</CodeBox>
<h4>Dynamic attributes</h4>
<p>Manejar los atributos dinámicamente.</p>
<CodeBox>
  &num; Dynamic attributes 
  &lt;script&gt; 
    let src = 'tutorial/image.gif'; 
    let name = 'Rick Astley'; 
  &lt;/script&gt; 
  
  &lt;img &lcub;src&rcub; alt="&lcub;name&rcub; dances."&gt;
</CodeBox>
<h4>HTML tags</h4>
<p>Renderizar HTML directamente en el componente.</p>
<CodeBox>
  &num; HTML tags 
  &lt;script&gt; 
    let string = `this string contains some &lt;strong&gt;HTML!!!&lt;/strong&gt;`
  &lt;/script&gt; 

  &lt;p&gt;&lcub@html string&rcub&lt;/p&gt;
</CodeBox>
<h4>Conditional blocks</h4>
<p>Renderizar HTML condicionalmente.</p>
<CodeBox>
  &num; Conditional blocks 
  &lt;script&gt; 
    let x = 7; 
  &lt;/script&gt; 
  
  &lcub;#if x &gt; 10&rcub; 
    &lt;p&gt;&lcub;x&rcub; is greater than 10&lt;/p&gt; 
  &lcub;:else if 5 &gt; x&rcub; 
    &lt;p&gt;&lcub;x&rcub; is less than 5&lt;/p&gt;
  &lcub;:else&rcub; 
    &lt;p&gt;&lcub;x&rcub; is between 5 and 10&lt;/p&gt;
  &lcub;/if&rcub;
</CodeBox>
<h4>Each blocks</h4>
<p>Iterar data en el HTML.</p>
<CodeBox>
  &num; Each blocks 
  &lt;script&gt; 
    export let links = &lsqb; 
    &lcub name: "About", to: "/about/Paz" &rcub, 
    &lcub name: "Basics", to: "/basics" &rcub,
    &lcub name: "Home", to: "/" &rcub, 
  &rsqb;; 
  &lt;/script&gt; 
  
  &lcub;#each links as link&rcub; 
    &lt;ul&gt; 
      &lt;NavLink to=&lcub;link.to&rcub;&gt;&lcub;link.name&rcub;&lt;/NavLink&gt;
    &lt;/ul&gt; 
  &lcub;/each&rcub;
</CodeBox>
<h4>Await blocks</h4>
<p>Renderizar HTML directamente en el componente.</p>
<CodeBox>
  &num; Await blocks
  &lcub;#await promise&rcub; 
    &lt;p&gt;...waiting&lt;/p&gt;
  &lcub;:then pokemon&rcub;
    &lt;p&gt;the pokemon is&lt;/p&gt;
    &lt;img src=&lcub;pokemon.sprites.front_default&rcub; alt=""&gt;
  &lcub;:catch error&rcub;
    &lt;p style="color: red"&gt;&lcub;error.message&rcub;&lt;/p&gt;
  &lcub;/await&rcub;
</CodeBox>
<div class="input-field inline">
  <input id="email_inline" type="email" class="validate" bind:value={pokemon}>
  <label for="email_inline">Busca un pokemon</label>
</div>
<button class="btn waves-effect waves-light" name="action" on:click={handleClick}>buscar
  <i class="material-icons right">send</i>
</button>
{#await promise}
  <p>...waiting</p>
{:then pokemon}
  <p>the pokemon is</p>
  <img src={pokemon.sprites.front_default} alt="">
{:catch error}
  <p style="color: red">No se encontró pokemon</p>
{/await}
<h4>Events</h4>
<CodeBox>
  &num; Events
  &lt;script&gt;
    let message = "";
    const sayHello = () =&gt; &lcub;
      message = "Hello!";
    &rcub;
  &lt;/script&gt; 

  &lt;a class="waves-effect waves-light btn" on:click=&lcub;sayHello&rcub;&gt;
    say hello
  &lt;/a&gt;
  &lcub;#if message !== ''&rcub; 
    &lt;p&gt;&lcub;message&rcub;&lt;/p&gt;
  &lcub;/if&rcub;
</CodeBox>
<a class="waves-effect waves-light btn" on:click={sayHello}>say hello</a>
<div class="answer">
  {#if message !== ''} 
    <p>{message}</p>
  {/if}
</div>

<div>
  <button class="btn waves-effect waves-light" name="action" on:click={goNext}>Siguiente
    <i class="material-icons right">send</i>
  </button>
</div>

<style>
  .answer {
    min-height: 60px;
  }
</style>
