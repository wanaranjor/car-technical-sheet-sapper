<script>
  import Sidebar from '../components/Sidebar.svelte';
  import Topbar  from '../components/Topbar.svelte';
  import SearchForm from '../components/SearchForm.svelte';
  import SearchResults from '../components/SearchResults.svelte';
  import AddVehicle from '../components/AddVehicle.svelte';
  import axios from 'axios';

  let resultsVehiculos = "";
  let resultsMarca = "";
  let resultsLinea = "";
  let resultsMarcaCount = "";

  const searchVehiculos = async (event) => {
    const marcaId = event.detail.selectedMarca;
    const lineaId = event.detail.selectedLinea;
    console.log(marcaId, lineaId)
    if(marcaId && !lineaId){
      try {
        const url = `http://localhost:3001/api/marcas/`+ marcaId + `/vehiculos`;
        const response = await axios.get(url);
        resultsVehiculos = response.data;
         console.log(resultsVehiculos);

        const urlMarca = `http://localhost:3001/api/marcas/`+ marcaId;
        const responseMarca = await axios.get(urlMarca);
        resultsMarca = responseMarca.data.marca;

        const urlCount = `http://localhost:3001/api/marcas/`+ marcaId + `/vehiculos/count`;
        const responseCount = await axios.get(urlCount);
        resultsMarcaCount = responseCount.data.count;
      }
      catch(e) {
          console.error("Error al cargar Marcas:", e );
      }
    }

    if(marcaId && lineaId){
      try {
          const urlLinea = `http://localhost:3001/api/lineas/`+ lineaId + `/vehiculos`;
          const responseLinea = await axios.get(urlLinea);
          resultsVehiculos = responseLinea.data;
          console.log(resultsVehiculos);

          const urlCount = `http://localhost:3001/api/lineas/`+ lineaId + `/vehiculos/count`;
          const responseCount = await axios.get(urlCount);
          resultsMarcaCount = responseCount.data.count;
      }
      catch(e) {
          console.error("Error al cargar Marcas Lineas:", e );
      }
    }
  }
</script>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <SearchForm on:searchOptions={searchVehiculos} {resultsMarcaCount}/>
  <SearchResults {resultsVehiculos} {resultsMarca} {resultsMarcaCount}/>
  <AddVehicle />
</div>