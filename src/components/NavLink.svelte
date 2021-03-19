<script>
  import { Link } from "svelte-routing";
  import { get } from "svelte/store";
  import { currentPath } from "../stores/PathStore";

  export let to = "";

  const updatePath = () => {
    currentPath.set(to);
    console.log(get(currentPath));
  };
</script>

<Link {to} on:click={updatePath}>
  <slot />
</Link>
