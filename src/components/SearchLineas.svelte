<script>
  import { createEventDispatcher } from 'svelte';
  import axios from 'axios';
  export let nameMarca;
  export let marcaLineas;
  
  let searchLineas = '';
</script>

<div class="p-3">
  <div class="flex flex-wrap items-center text-white  rounded-t border-l border-t border-r  bg-blue-500 px-4 py-1 font-bold">
    <span class="flex-auto">{nameMarca.marca} : Consultar Lineas 
      <span class="bg-yellow-500 text-white font-bold py-1 px-2 ml-3 rounded-full">{marcaLineas.length}</span>
    </span>
  </div>
  <div class="text-black rounded-b px-4 py-2 flex flex-col border">
    <div class="-mx-3 md:flex mb-2">
      <div class="md:w-1/5 px-3">
          <label class="block uppercase tracking-wide text-grey-700 text-xs font-bold mb-1" for="marca">
            Lineas
          </label>
          <input
          id="marca"
          name="marca"
          type="text"
          bind:value={searchLineas}
          class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-1 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500 uppercase"
          />
      </div>
    </div>
  </div>
</div>
