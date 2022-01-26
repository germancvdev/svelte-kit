<script>
	import '../app.css';
</script>

<header class="bg-purple-500 py-5  text-white  shadow-md  fixed w-full z-50 ">
	<div class="container mx-auto flex justify-between items-center">
		<h1 class="my-0">Giphys</h1>
		<button class="bg-purple-800 px-3 py-1 my-0 rounded-sm hover:bg-purple-900">Login</button>
	</div>
</header>
<main class="container mx-auto pt-20">
	<slot />
</main>
