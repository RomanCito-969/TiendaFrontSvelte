<script>
  import { getContext } from "svelte";
  import { data } from "./store.js";
  import { onMount } from "svelte";
  import Buscar from "./Buscar.svelte";
  import Articulo from "./Articulo.svelte";
  import Boton from "./Boton.svelte";

  const URL = getContext("URL");

  let artInsertar = {};
  let datosFiltrados = [];
  let patron;
  let getArticulos = async () => {
    const response = await fetch(URL.articulos);
    $data = await response.json();
  };

  onMount(getArticulos);

  $: datosFiltrados = $data.filter((articulo) =>
    RegExp(patron, "i").test(articulo.nombre)
  );
</script>

<Buscar bind:busqueda={patron} />

<h1>Esta en Articulo</h1>

<Articulo bind:articulo={artInsertar}>
  <Boton tipo="insertar" documento={artInsertar} />
</Articulo>
<hr />
<section class="listaAticulos">
  {#each datosFiltrados as articulo}
    <div>
      <Articulo bind:articulo>
        <br />
        <Boton tipo="modificar" documento={articulo} />
        <Boton tipo="eliminar" documento={articulo} />
      </Articulo>
    </div>
  {/each}
</section>
<hr />

<style>
  .listaAticulos {
    display: grid;
    grid-template-columns: auto auto auto auto;
    grid-gap: 5px;
  }
</style>
