<script>
  import Sidebar from '../components/Sidebar.svelte';
  import Topbar  from '../components/Topbar.svelte';
  import SearchForm from '../components/SearchForm.svelte';
  import SearchResults from '../components/SearchResults.svelte';
  // import AddVehicle from '../components/AddVehicle.svelte';
  import axios from 'axios';

  let resultsVehiculos = "";
  let searchResultsMarcas = [];
  let resultsLinea = "";
  let resultsMarcaCount = "";
  let Marcas;

  const handlerListMarcas = (event) => {
    searchResultsMarcas = event.detail.resultsMarcas;    
    console.log(searchResultsMarcas);
  }
</script>

<svelte:head>
	<title>Tablero</title>
</svelte:head>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <!-- <SearchForm on:searchOptions={searchVehiculos} {resultsMarcaCount}/> -->
  <SearchForm on:resultsMarcas={handlerListMarcas}/>
  <!-- <SearchResults {resultsVehiculos} {resultsMarca} {resultsMarcaCount}/> -->
  <SearchResults {searchResultsMarcas}/>
  <!-- <AddVehicle /> -->
</div>