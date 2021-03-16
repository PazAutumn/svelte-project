<script>
import NavLink from './NavLink.svelte'
import { Link } from "svelte-routing"
export let links = []
</script>

<div class="nav-wrapper">
  <Link to="#" class="brand-logo">Logo</Link>
	{#each links as link}
    <ul id="nav-mobile" class="right hide-on-med-and-down">
			<NavLink to={link.to}>{link.name}</NavLink>
    </ul>
	{/each}
</div>

<style type="text/scss">
  .nav-wrapper {
    padding: 0 5px;
    #nav-mobile {
      :global(a) {
        color: white;
      }
      :global(a):hover {
        text-decoration: none;
      }
    }
  }
</style>