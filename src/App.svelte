<script>
	import { Router, Route } from "svelte-routing";
	import Navbar from "./components/Navbar.svelte"
	import Home from "./routes/Home.svelte";
	import About from "./routes/About.svelte";
	import Blog from "./routes/Blog.svelte";
  
	// Used for SSR. A falsy value is ignored by the Router.
	export let url = "";
	export let navbarLinks = [
		{name: 'Blog', to: 'blog'},
		{name: 'About', to: 'about/pachi'},
		{name: 'Home', to: '/'},
	]
  </script>
  
  <Router url="{url}">
	<nav>
	  <Navbar links={navbarLinks}/>
	</nav>
	<div>
	  <Route path="blog/*" component="{Blog}" />
	  <Route path="/" component="{Home}" />
	  <Route path="about/:name" let:params>
			<About name={params.name}/>
		</Route>
	</div>
  </Router>