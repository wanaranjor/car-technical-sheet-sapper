<script>
  import Sidebar from '../components/Sidebar.svelte';
  import Topbar  from '../components/Topbar.svelte';
  import SearchForm from '../components/SearchForm.svelte';
  import SearchResults from '../components/SearchResults.svelte';
  import AddVehicle from '../components/AddVehicle.svelte';
</script>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <SearchForm />
  <SearchResults />
  <AddVehicle />
</div>