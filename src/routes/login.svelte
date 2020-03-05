<script>

  import { onMount } from 'svelte';

	let bg;

	onMount(() => {
    bg = Math.floor(Math.random() * (5 - 1) + 1);
	});
  

</script>
<div class="bg-cover bg-center h-screen w-screen text-white" style="background-image: url(./bg{bg}.jpg">
  <div class="flex justify-end items-center flex-1 h-full px-4 sm:px-0">
    <div class="flex flex-col rounded w-full md:w-1/4 bg-transparent sm:mx-0 md:mr-32">
      <div class="w-full p-4">
        <div class="flex-1 justify-center mb-8">
          <h1 class="text-4xl text-center font-thin">24-Automotor</h1>
          <div class="w-full mt-4">
            <form class="w-3/4 mx-auto">
              <div class="flex flex-col mt-4">
                  <input id="email" type="text" class="flex-grow h-8 px-2 border rounded text-black border-grey-400" name="email" value="" placeholder="Email">
              </div>
              <div class="flex flex-col mt-4">
                  <input id="password" type="password" class="flex-grow h-8 px-2 rounded border text-black border-grey-400" name="password" required placeholder="Password">
              </div>
              <div class="flex flex-col mt-8">
                  <button type="submit" class="bg-transparent hover:bg-blue-500 text-white font-semibold hover:text-white py-2 px-4 border border-white hover:border-transparent rounded">
                      Login
                  </button>
              </div>
            </form>
            <div class="text-center mt-4">
                <a class="no-underline hover:underline text-blue-dark text-xs" href="/">
                    Forgot Your Password?
                </a>
            </div>
            <div class="w-3/4  mx-auto text-xs mt-4">
              <p>
                  Está ingresando a un sistema de información de propiedad de la
                  Policía Nacional, su uso no autorizado incurre en el incumplimiento
                  de las políticas de seguridad de la Institución establecidas en el
                  Manual del Sistema de Gestión de Seguridad de la Información para la
                  Policía Nacional y acarrea sanciones penales, disciplinarias y/o
                  administrativas a que haya lugar; ayúdenos a prevenir la divulgación
                  no autorizada, perdida y/o fuga de la información institucional.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>