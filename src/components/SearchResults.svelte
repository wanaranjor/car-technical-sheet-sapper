<script>
  export let resultsVehiculos;
  export let resultsMarcaCount;
  export let resultsMarca;
  export let resultsLinea;
  export let resultsClase;
  export let resultsModelo;
  console.log(resultsVehiculos)
</script>

<div class="px-3 overflow-x-auto overflow-y-auto">
  <p class="text-white bg-blue-500 px-4 py-1 font-bold rounded-t border-l border-t border-r">
    Resultados Busqueda:
    <!-- {#if resultsMarcaCount} -->
      <span class="bg-yellow-500 text-white font-bold py-1 px-2 ml-3 rounded-full">
        {resultsMarcaCount}
      </span>
    <!-- {/if} -->
  </p>
  <div class="flex flex-row flex-wrap">
  {#each resultsVehiculos as vehiculo}
  <div class="w-full sm:w-1/2 md:w-1/4 mb-3 px-2">
    <div class="">
      <div class="mt-3 max-w-sm overflow-hidden border">
        <!-- <img class="w-full" src="https://tailwindcss.com/img/card-top.jpg" alt="Sunset in the mountains"> -->
        <div class="px-6 py-4">
          <div class="font-bold text-xl mb-2">{vehiculo.vehiculo}</div>
          <p class="text-gray-700 text-base">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
          </p>
        </div>
        <div class="px-6 py-4">
          <span class="inline-block bg-gray-200 px-3 py-1 text-sm font-semibold text-gray-700 mr-2">
            #{resultsMarca}
          </span>
          <span class="inline-block bg-gray-200 px-3 py-1 text-sm font-semibold text-gray-700 mr-2">
            #{resultsLinea}
          </span>
          <span class="inline-block bg-gray-200 px-3 py-1 text-sm font-semibold text-gray-700">
            #{resultsClase}
          </span>
          <span class="inline-block bg-gray-200 px-3 py-1 text-sm font-semibold text-gray-700">
            #{resultsModelo}
          </span>
        </div>
      </div>
    </div>
    </div>
  {/each}
  </div>
</div>