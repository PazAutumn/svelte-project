<script>
  export let frameworkName = '';
  export let src = '';
</script>

<div class="box code white-code">
  <div class="framework">{frameworkName.toUpperCase()}</div>
  <img src={src} alt="code-example" />
</div>

<style type="text/scss">
.white-code {
  background-color: #f6fafd;
  .framework {
	font-family: "Overpass", sans-serif;
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
	font-family: "Fira Mono", monospace;
	border-radius: 0.5em;
	margin: 20px;
	display: flex;
	justify-content: left;
	position: relative;
	padding: 5px;
}
</style>