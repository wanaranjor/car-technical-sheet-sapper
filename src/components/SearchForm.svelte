<script>
  import { fade } from 'svelte/transition';
  import axios from 'axios';

  let marcas = [];
  let searchMarca = "";
  // let marcasResults = "";

  let checkedClase = false;
  let checkedMarca = false;
  let checkedLinea = false;
  let checkedModelo = false;

  let selectedMarca = '';

  $: if(checkedMarca) getAllMarcas()

  // $: marcas = marcasResults

  // $: if(searchMarca.length >= 2) {
  //   getSearchMarcas()
  // }

  // const getSearchMarcas = async () => {
  //   try {
  //     const url = `http://localhost:3001/api/marcas?filter[where][marca][like]=`+ searchMarca + `%`;
  //     const response = await axios.get(url);
  //     console.log(url, response.data);
  //     marcasResults = response.data;
  //   }
  //   catch(e) {
  //       console.error("Error al cargar Marcas:", e );
  //   }
  // }

  const getAllMarcas = async () => {
    try {
      const url = `http://localhost:3001/api/marcas`;
      const response = await axios.get(url);
      marcas = response.data;
    }
    catch(e) {
        console.error("Error al cargar Marcas:", e );
    }
  }

  const handleChecked = () => {
    console.log(selectedMarca)
  }

</script>

<div class="p-3">

  <div class="flex flex-wrap items-center text-white  rounded-t border-l border-t border-r  bg-blue-500 px-4 py-1 font-bold">
    <span class="flex-auto">Consultar Vehículo</span>
    <label class="px-2">
      <input type=checkbox bind:checked={checkedClase} />
        Clase
    </label>
    <label class="px-2">
      <input type=checkbox bind:checked={checkedMarca} />
        Marca
    </label>
    <label class="px-2">
      <input type=checkbox bind:checked={checkedLinea} />
        Línea
    </label>
    <label class="px-2">
      <input type=checkbox bind:checked={checkedModelo} />
        Modelo
    </label>
    {#if checkedClase || checkedMarca || checkedLinea || checkedModelo}
      <div transition:fade class="bg-white hover:bg-yellow-500 text-blue-700 hover:text-white px-2 border border-blue-500 hover:border-yellow-500 rounded">
        <button on:click={handleChecked}>
          Buscar
        </button>
      </div>
    {/if}
  </div>
  <div class="text-black rounded-b px-4 py-2 flex flex-col border">
    <div class="-mx-3 md:flex mb-2">
      {#if checkedClase}
        <div transition:fade class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="clase">
            Clase
          </label>
          <input
            class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-1 px-4"
            id="clase"
            type="text"
            bind:value={searchMarca}
            placeholder="Clase" />
            {searchMarca}
        </div>
      {/if}
      {#if checkedMarca}
        <div transition:fade class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="marca">
            Marca
          </label>
          <input type="text" list="marcaName" class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-1 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          bind:value={selectedMarca}/>
          <datalist id="marcaName">
            {#each marcas as marca}
              <option value={marca.marca}>{marca.marca}</option>
            {/each}
          </datalist>
        </div>
      {/if}
      {#if checkedLinea}
        <div transition:fade class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="linea">
            Línea
          </label>
          <input
            class="realtive appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-1 px-4"
            id="linea"
            type="text"
            placeholder="Línea" />
            <!-- TODO: pendiente lupa de busqueda -->
        </div>
      {/if}
      {#if checkedModelo}
        <div transition:fade class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="modelo">
            Modelo
          </label>
          <input
            class="appearance-none block w-full text-sm leading-tight text-gray-700 border rounded focus:outline-none focus:shadow-outline py-1 px-4"
            id="modelo"
            type="text"
            placeholder="Modelo" />
        </div>
      {/if}
    </div>
  </div>
</div>