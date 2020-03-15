<script>
  import { ChevronRightIcon } from 'svelte-feather-icons';
  export let filterMarcaLineas;
</script>

<div class="px-3 overflow-x-auto overflow-y-auto my-3">
  <p class="text-white bg-blue-500 px-4 py-1 font-bold rounded-t border-l border-t border-r">
    Resultados Lineas:
    {#if filterMarcaLineas}
      <span class="bg-yellow-500 text-white font-bold py-1 px-2 ml-3 rounded-full">
        {filterMarcaLineas.length}
      </span>
    {/if}
  </p>
  <div class="flex flex-row flex-wrap">
    {#each filterMarcaLineas as linea, i (linea.id)}
      <div class="w-full sm:w-1/2 md:w-1/4 mb-3 px-2">
        <div class="mt-3 overflow-hidden border">
          <div class="pr-4 p-3 text-gray-700 hover:bg-gray-200 hover:text-blue-700">
            <a class="flex items-center" href="/marcas/lineas/{linea.id}">
              <ChevronRightIcon size="1x"/>
              <h3 class="px-3 font-bold text-base">{linea.linea}</h3>
            </a>
          </div>
        </div>
      </div>
    {/each}
  </div>
</div>