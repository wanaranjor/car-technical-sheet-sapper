<script>
  import { FileTextIcon } from 'svelte-feather-icons';
</script>

<table class="w-full table-fixed shadow text-base">
  <thead>
    <tr class="bg-gray-100">
      <th class="w-1/5 border px-4 py-2 text-left">Item</th>
      <th class="w-4/5 border px-4 py-2 text-left">Valor</th>
    </tr>
  </thead>
  <tbody>
    <tr class="hover:bg-gray-100">
      <td class="border px-4 py-2 bg-gray-100 font-semibold">Chasis</td>
      <td class="border px-4 py-2">??????</td>
    </tr>
    <tr class="hover:bg-gray-100">
      <td class="border px-4 py-2 bg-gray-100 font-semibold">Motor</td>
      <td class="border px-4 py-2">?????</td>
    </tr>
    <tr class="hover:bg-gray-100">
      <td class="border px-4 py-2 bg-gray-100 font-semibold">Plaqueta / Sticker</td>
      <td class="border px-4 py-2">??????</td>
    </tr>
    <tr class="hover:bg-gray-100">
      <td class="border px-4 py-2 bg-gray-100 font-semibold">Superficie</td>
      <td class="border px-4 py-2">?????</td>
    </tr>
  </tbody>
</table>
<div class="border rounded shadow mt-3">
  <div class="flex items-center border-b px-3 py-2 -mb-px bg-gray-100">
    <FileTextIcon size="1x" />
    <h3 class="font-semibold text-base px-2">Observaciones</h3>
  </div>
  <div class="text-left px-3 py-2">
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laborum molestiae recusandae ab quos nostrum voluptatem debitis fuga, expedita consequuntur iste voluptatum aspernatur. Optio officia rerum distinctio ex incidunt ducimus porro!</p>
  </div>
</div>