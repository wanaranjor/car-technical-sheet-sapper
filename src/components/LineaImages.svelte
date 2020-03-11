<script>
  import Carousel from '@beyonk/svelte-carousel';
	import { ChevronLeftIcon, ChevronRightIcon } from 'svelte-feather-icons';
</script>

<div class="demo">
	<Carousel perPage={1}>
		<span class="control" slot="left-control">
			<ChevronLeftIcon />
		</span>
		<div class="flex flex-col">  
      <img src="https://lh3.googleusercontent.com/proxy/hw5sieXLNQBb6xK-I3kaV53pIEXdVLc3_TaGTD2eFnMHgrnXa3oW4NFnaM4Amhwt2d2Y_T-c3EwSfsjyBr5W_Gc-RaBJXwHiRrs7BwZTbK3d6kcmAef-4yI" alt="img">
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


<style>
  .control :global(svg) {
        width: 100%;
        height: 100%;
        color: #ccc;
        border: 2px solid #ccc;
        border-radius: 32px;
    }
</style>