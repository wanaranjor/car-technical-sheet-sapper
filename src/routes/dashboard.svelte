<script>
  import Sidebar from '../components/Sidebar.svelte';
  import Topbar  from '../components/Topbar.svelte';
  import SearchForm from '../components/SearchForm.svelte';
</script>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <SearchForm />
</div>