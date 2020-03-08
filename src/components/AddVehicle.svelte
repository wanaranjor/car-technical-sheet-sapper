<script context="module">
	export async function preload(page, session) {
		const { id } = page.params;

		

		return { id };
	}
</script>
<script>
  export let id;
  console.log(id);

</script>


<div class="p-3">
  <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
    Agregar Vehículo
  </button>
</div>