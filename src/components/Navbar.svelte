<script>
import NavLink from './NavLink.svelte'
import { Link } from "svelte-routing"
  export let links = []
  let logo = 'assets/img/svelte-logo-horizontal.svg'
</script>
<div class="navbar-fixed">
  <nav>
    <div class="nav-wrapper">
      <Link to="/" class="brand-logo">
        <img src={logo} alt="logo">
      </Link>
      {#each links as link}
        <ul id="nav-mobile" class="right hide-on-med-and-down">
          <NavLink to={link.to}>{link.name}</NavLink>
        </ul>
      {/each}
    </div>
  </nav>
</div>



<style type="text/scss">
nav {
  background-color: white;
  img {
    height: 40px;
  }
  .nav-wrapper {
    padding: 0 5px;
    #nav-mobile {
      :global(a) {
        color: black;
        font-weight: 300;
      }
      :global(a):hover {
        text-decoration: none;
      }
    }
  }  
}

</style>