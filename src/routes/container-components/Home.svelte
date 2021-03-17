<script>
  import { Router, Route } from "svelte-routing";
  import Welcome from "../presentation-components/Welcome.svelte";
  import WriteLessCode from "../presentation-components/WriteLessCode.svelte";
  import TrulyReactive from '../presentation-components/TrulyReactive.svelte';
  import NoVirtualDOM from '../presentation-components/NoVirtualDOM.svelte';

  export let location;
</script>

<div class="row">
  <Router>
    <div class="col s4 left-col">
      <Welcome />
    </div>
    <div class="col s8 right-col">
      {#if location.pathname === "/"}
        <div class="home">
          <img src={"/assets/img/svelte-logo-outline.svg"} alt="" />
          <img src={"/assets/img/svelte-logotype.svg"} alt="svelte-logotype" />
          <img src={"/assets/img/svelte-logo-outline.svg"} alt="" />
        </div>
      {:else}
        <Route path="write-less-code">
          <WriteLessCode />
        </Route>
        <Route path="no-virtual-dom">
          <NoVirtualDOM/>
        </Route>
        <Route path="truly-reactive">
          <TrulyReactive></TrulyReactive>
        </Route>
      {/if}
    </div>
  </Router>
</div>

<style type="text/scss">
  .row {
    font-family: "Overpass", sans-serif;
    .left-col {
      position: fixed;
      overflow: auto;
      padding-top: 50px;
      top: 0;
      bottom: 0;
      height: 100%;
      background-color: #676778;
      color: #f1f1f3;
    }
    .right-col {
      background-image: url("/assets/img/svelte-logo-outline.svg");
      background-size: 20px;
      float: right;
      padding: 40px;
      overflow: auto;
      padding-top: 50px;
      top: 0;
      bottom: 0;
      height: 93vh;
      color: #444444;
      .home {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100%;
        width: 100%;
      }
      img {
        height: 55px;
      }
    }
  }
</style>
