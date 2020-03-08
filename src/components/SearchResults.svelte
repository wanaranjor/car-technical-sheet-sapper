<script>
  export let resultsVehiculos;
  export let resultsMarcaCount;
  export let resultsMarca;
  export let resultsLinea;
  // export let resultsClase;
  // export let resultsModelo;
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
    
      <div class="w-full md:w-1/5 p-3">
        <div class="hover:bg-gray-200 border rounded p-2">
          <div class="flex flex-row items-center">
            <div class="flex-shrink pr-4">
              <div class="p-3 text-gray-700 hover:text-blue-700">
                <a href="vehiculos/{vehiculo.id}">
                  <i class="fas fa-car fa-3x fa-fw"></i>
                </a>
              </div>
            </div>
            <div class="flex-1 text-right md:text-center">
              {resultsMarca}
              {resultsLinea}
              <h3 class="font-bold uppercase text-orange-600">{vehiculo.vehiculo}</h3>
              <h5 class="font-bold">NIT</h5>
              <h6 class="uppercase text-gray-500">ADDRES</h6>
            </div>
          </div>
        </div>
      </div>

    {/each}
  </div>
</div>