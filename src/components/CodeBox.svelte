<script>
  export let title = "";
  export let src = "";
</script>

<div class="white-code">
  {#if title}
  <div class="framework">{title.toUpperCase()}</div>
  {/if}
  <pre>
    <code class='code'>
      {#if src}
      <img {src} alt="code-example" />
      {/if}
      <slot/>
    </code>
  </pre>
</div>

<style type="text/scss">
  .white-code {
    background-color: #f6fafd;
    position: relative;
    border-radius: 0.5em;
    display: flex;
    .framework {
      font-family: "Overpass", sans-serif !important;
      color: #f6fafd;
      background-color: #575766;
      border-radius: 0.5em;
      padding: 5px;
      position: absolute;
      right: 0;
    }
    img {
      height: 100%;
    }
  }
  .code {
    font-family: "Fira Mono", monospace !important;
    margin: 20px;
    display: flex;
    justify-content: left;
    font-size: 13px;
    padding: 5px;
    line-height: 25px;
    letter-spacing: 0.5px;
  }
</style>
