<script>
  export let articulo = {
    nombre: "",
    precio: 0,
  };
</script>

<input
  type="text"
  id="nombre"
  placeholder="Nombre"
  bind:value={articulo.nombre}
/>
<input
  type="number"
  id="precio"
  placeholder="Precio"
  bind:value={articulo.precio}
/>
<slot />

<style></style>
