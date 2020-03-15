<script context="module">
  import axios from 'axios';
  import LineaTable from '../../../components/LineaTable.svelte';
  import LineaImages from '../../../components/LineaImages.svelte';

	export async function preload(page) {
    const { slug } = page.params;
    const urlLineas = `http://localhost:3001/api/lineas/${slug}`;
    const responseLinea = await axios.get(urlLineas);
    const detailLinea = await responseLinea.data;

    const urlMarca = `http://localhost:3001/api/lineas/${slug}/marcas`;
    const responseMarca = await axios.get(urlMarca);
    const nameMarca = await responseMarca.data;

    return {detailLinea, nameMarca};
  }
</script>


<script>
  import Sidebar from '../../../components/Sidebar.svelte';
  import Topbar  from '../../../components/Topbar.svelte';

  export let detailLinea;
  export let nameMarca;
</script>

<svelte:head>
	<title>Linea Detalle</title>
</svelte:head>

<Sidebar />

<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <div class="px-4 overflow-x-auto overflow-y-auto mt-3">
    <div class="bg-white border-t border-b sm:border-l sm:border-r sm:rounded shadow mb-6 mx-3">
      <div class="flex">
        <div class="w-1/4 flex-col text-center py-1">
          <div class="border-r flex flex-col">
            <span class="text-2xl font-semibold">
              {nameMarca.marca}
            </span>
            <span class="text-sm uppercase text-gray-600 tracking-wide">
              Marca
            </span>
          </div>
        </div>
        <div class="w-1/4 text-center py-1">
          <div class="border-r flex flex-col">
            <span class="text-2xl font-semibold">
              {detailLinea.linea}
            </span>
            <span class="text-sm uppercase text-gray-600 tracking-wide">
              Línea
            </span>
          </div>
        </div>
        <div class="w-1/4 text-center py-1">
          <div class="border-r flex flex-col">
            <span class="text-2xl font-semibold">
              2018
            </span>
            <span class="text-sm uppercase text-gray-600 tracking-wide">
              Modelo
            </span>
          </div>
        </div>
        <div class="w-1/4 text-center py-1">
          <div class="border-r flex flex-col">
            <span class="text-2xl font-semibold">
              AUTOMOVIL
            </span>
            <span class="text-sm uppercase text-gray-600 tracking-wide">
              Clase
            </span>
          </div>
        </div>
      </div>
    </div>
    <div class="flex flex-wrap">
      <div class="w-full md:w-1/2 mb-6 lg:mb-0 px-3 flex flex-col">
        <LineaTable />
      </div>
      <div class="w-full md:w-1/2 px-4">
        <LineaImages />
      </div>
    </div>
  </div>
</div>

