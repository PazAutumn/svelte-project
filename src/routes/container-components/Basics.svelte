<script>
  import { Link } from "svelte-routing";
</script>

<h1>Basics</h1>
<h5>En esta sección veremos los conocimientos escenciales para utilizar Svelte</h5>

<Link to="/getting-started">
  <div class="box gray">Getting started</div>
</Link>
<Link to="/routing">
  <div class="box gray">Routing</div>
</Link>
<Link to="/essentials">
  <div class="box gray">Svelte essentials</div>
</Link>
<Link to="/bonus-track">
  <div class="box gray">BonusTrack</div>
</Link>
<style>
  h1,
  h5 {
    text-align: center;
  }
</style>
