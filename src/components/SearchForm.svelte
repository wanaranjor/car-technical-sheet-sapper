<script>
  import { createEventDispatcher } from 'svelte';
  import axios from 'axios';

  let searchMarcas = '';
  let resultsMarcas = [];

  const dispatch = createEventDispatcher();

  $: if(searchMarcas.length >= 2) {
    getMarcas()
  }

  const getMarcas = async () => {
      try {
      const url = `http://localhost:3001/api/marcas?filter[where][marca][ilike]=%${searchMarcas}%`;
      const response = await axios.get(url);
      resultsMarcas = response.data;
      console.log(resultsMarcas);
      dispatch('resultsMarcas', {resultsMarcas})
      }
      catch(e) {
        console.error("Error al cargar Marcas:", e );
      }
    }
</script>

<div class="p-3">
  <div class="flex flex-wrap items-center text-white  rounded-t border-l border-t border-r  bg-blue-500 px-4 py-1 font-bold">
    <span class="flex-auto">Consultar Marca</span>
  </div>
  <div class="text-black rounded-b px-4 py-2 flex flex-col border">
    <div class="-mx-3 md:flex mb-2">
      <div class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="marca">
            Marcas
          </label>
          <input
          id="marca"
          name="marca"
          type="text"
          bind:value={searchMarcas}
          class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-1 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500 uppercase"
          />
      </div>
    </div>
  </div>
</div>