<script>
  import axios from 'axios';
  import Swal from 'sweetalert2'

  let marca = '';

  const handleSubmit = () => {
    Swal.fire({
      title: `Esta seguro de crear la marca: ${marca} ?`,
      text: "¡No podrás revertir esto!",
      icon: 'warning',
      showCancelButton: true,
      confirmButtonText: 'Si, crear!',
      cancelButtonColor: '#d33',
      cancelButtonText: 'Cancelar'
    }).then(async(result) => {
      if (result.value) {
        await addMarca();
        Swal.fire(
          'Deleted!',
          'Your file has been deleted.',
          'success'
        )
      } else {
        marca = '';
      }
    })
  }

  const addMarca = async () => {
    try {
      const url = `http://localhost:3001/api/marcas`;
      const response = await axios.post(url,{
        marca: marca.trim().toUpperCase()
      });
      }
    catch(e) {
        console.error("Error al crear Marca:", e );
      }
  }

</script>

<div class="px-3 overflow-x-auto overflow-y-auto mt-3">
  <div class="w-full max-w-xs">
    <form on:submit|preventDefault={handleSubmit} class="bg-white border rounded px-8 pt-6 pb-8 mb-4">
      <div class="mb-4">
        <label class="block text-gray-700 text-lg font-bold mb-2" for="marca">
          Marcas
        </label>
        <input
          id="marca"
          type="text"
          bind:value={marca}
          placeholder="Marca"
          class="appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        />
      </div>
      <div class="flex items-center justify-between">
        {#if marca}
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline" type="submit">
            Crear
          </button>
        {/if}
      </div>
    </form>
  </div>
</div>