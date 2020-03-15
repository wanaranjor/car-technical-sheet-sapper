<script>
  import Carousel from '@beyonk/svelte-carousel';
	import { ImageIcon, ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons';
</script>

<div class="border rounded shadow">
  <div class="flex items-center border-b px-6 py-2 -mb-px bg-gray-100">
    <ImageIcon size="1x" />
    <h3 class="font-semibold text-base px-2">Imágenes Improtas</h3>
  </div>
  <div class="text-center px-6 py-4">
    <div class="demo">
      <Carousel perPage={1}>
        <span class="control" slot="left-control">
          <ChevronLeftIcon />
        </span>
        <div class="flex flex-col">  
          <img src="https://todotransitobogota.files.wordpress.com/2014/06/impronta.jpg" alt="img">
          <span>Imagen 1</span>
        </div>
        <div class="flex flex-col">  
          <img src="https://www.pruebaderuta.com/wp-content/uploads/2015/12/numero-identificacion-vehicular-1-620x264.jpg" alt="img">
          <span>Imagen 2</span>
        </div>
        <span class="control" slot="right-control">
          <ChevronRightIcon />
        </span>
      </Carousel>
    </div>
  </div>
</div>


<style>
  .control :global(svg) {
        width: 100%;
        height: 100%;
        color: #ccc;
        border: 2px solid #ccc;
        border-radius: 32px;
    }
</style>