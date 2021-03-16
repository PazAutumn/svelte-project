<script>
  import { Link } from "svelte-routing";
  
  export let to = "";
</script>

<Link to="{to}">
  <slot />
</Link>