<script>
  import { Route } from "svelte-routing";
  import Articulos from "./Articulos.svelte";
  import Clientes from "./Clientes.svelte";
  import Inicio from "./Inicio.svelte";
</script>

<main>
  <Route path="/" component={Inicio} />
  <Route path="/articulos" component={Articulos} />
  <Route path="/clientes" component={Clientes} />
</main>

<style>
  main {
    text-align: center;
  }
</style>
