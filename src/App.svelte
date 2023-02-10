<script>
	import Nav from "./Nav.svelte";
	import Contenido from "./Contenido.svelte";
	import {Router} from "svelte-routing"
</script>
<Router>
	<Nav/>
	<Contenido/>
</Router>

<style>
	:global(body){
		margin: 0 auto;
		padding: 0;
		background-color: whitesmoke;
	}
</style>