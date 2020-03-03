<script>
  import { onMount } from 'svelte';
  import axios from 'axios';
  let marcas = '';
  let selected;

  onMount(async () => {
    marcas = await getAllMarcas();
    console.log(marcas);
  });

  const getAllMarcas = async () => {
    try {
      const url = `http://localhost:3001/api/marcas`;
      const response = await axios.get(url);
      return response.data;
    }
    catch(e) {
        console.error("Error al cargar profile:", e );
    }
  };
</script>

<div class="px-6 py-3">
  <p class="text-white bg-blue-500 px-4 py-1 font-bold rounded-t border-l border-t border-r">Consultar Vehículo</p>
  <div class="text-black rounded-b px-4 py-2 flex flex-col border">
    <div class="-mx-3 md:flex">
      <div class="md:w-1/5 px-3">
        <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="placa">
          Placa
        </label>
        <input
          class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-2 px-4"
          id="placa"
          type="text"
          placeholder="Placa" />
      </div>
      <div class="md:w-1/5 px-3">
        <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="clase">
          Clase
        </label>
        <select bind:value={selected} class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-2 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-state">
          <option></option>
          {#each marcas as marca}
            <option value={marca.marca}>{marca.marca}</option>
          {/each}
        </select>
        <!-- <input
          class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-3 px-4"
          id="clase"
          type="text"
          value={marcas}
          on:input={handleInput}
          placeholder="Clase" /> -->
      </div>
      <div class="md:w-1/5 px-3">
        <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="marca">
          Marca
        </label>
        <input
          class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-2 px-4"
          id="marca"
          type="text"
          placeholder="Marca" />
      </div>
      <div class="md:w-1/5 px-3">
        <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="linea">
          Línea
        </label>
        <input
          class="realtive appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-3 px-4"
          id="linea"
          type="text"
          placeholder="Línea" />
          <!-- TODO: pendiente lupa de busqueda -->
      </div>
      <div class="md:w-1/5 px-3">
        <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="modelo">
          Modelo
        </label>
        <input
          class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-2 px-4"
          id="modelo"
          type="text"
          placeholder="Modelo" />
      </div>
    </div>
  </div>
</div>