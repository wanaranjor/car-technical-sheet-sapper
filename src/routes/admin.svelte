<script>
  import Sidebar from '../components/Sidebar.svelte';
  import Topbar  from '../components/Topbar.svelte';
  import Admin from '../components/Admin.svelte';
</script>

<svelte:head>
	<title>Administración</title>
</svelte:head>

<Sidebar />
<div class="flex-1 flex flex-col bg-white overflow-hidden">
  <Topbar />
  <Admin />
</div>