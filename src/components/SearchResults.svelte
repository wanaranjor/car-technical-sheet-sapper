<script>
  import { ChevronRightIcon } from 'svelte-feather-icons';
  export let searchResultsMarcas = [];
</script>

<div class="px-3 overflow-x-auto overflow-y-auto">
  <p class="text-white bg-blue-500 px-4 py-1 font-bold rounded-t border-l border-t border-r">
    Resultados Busqueda:
    {#if searchResultsMarcas}
      <span class="bg-yellow-500 text-white font-bold py-1 px-2 ml-3 rounded-full">
        {searchResultsMarcas.length}
      </span>
    {/if}
  </p>
  <div class="flex flex-row flex-wrap">
    {#each searchResultsMarcas as marca, i (marca.id)}
      <div class="w-full sm:w-1/2 md:w-1/4 mb-3 px-2">
        <div class="mt-3 overflow-hidden border">
          <div class="pr-4 p-3 text-gray-700 hover:bg-gray-200 hover:text-blue-700">
            <a href="marcas/{marca.id}" class="flex items-center">
              <ChevronRightIcon size="1x"/>
              <h3 class="px-3 font-bold text-base">{marca.marca}</h3>
            </a>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>