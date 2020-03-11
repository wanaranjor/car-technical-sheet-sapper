<script context="module">
  import axios from 'axios';

	export async function preload(page) {
    const { slug } = page.params;
    const urlLineas = `http://localhost:3001/api/marcas/${slug}/lineas`;
    const responseLineas = await axios.get(urlLineas);
    const marcaLineas = await responseLineas.data;

    const urlMarca = `http://localhost:3001/api/marcas/${slug}`;
    const responseMarca = await axios.get(urlMarca);
    const nameMarca = await responseMarca.data;
    console.log(nameMarca)

    return {nameMarca, marcaLineas};
  }
</script>

<script>
  import Sidebar from '../../components/Sidebar.svelte';
  import Topbar  from '../../components/Topbar.svelte';
  import SearchLineas from '../../components/SearchLineas.svelte';
  import MarcaLineas from '../../components/MarcaLineas.svelte'; 

  export let nameMarca;
  export let marcaLineas;  
</script>

<svelte:head>
	<title>Marcas Lineas</title>
</svelte:head>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <SearchLineas {nameMarca} {marcaLineas} />
  <MarcaLineas  {marcaLineas}/>
</div>