<script>
	import '../app.css';
</script>

<header class="bg-purple-500 py-5  text-white  shadow-md  fixed w-full z-50 ">
	<div class="container mx-auto flex justify-between items-center">
		<h1 class="my-0">Giphys</h1>

		<div>
			<a href="/" class="mx-2 hover:bg-purple-400 transition-colors px-4 py-2 rounded-sm">Home</a>
			<a href="/blog" class="mx-2 hover:bg-purple-400 transition-colors  px-4 py-2 rounded-sm"
				>Blog</a
			>
			<button class="bg-purple-800 px-3 ml-2 py-1 my-0 rounded-sm hover:bg-purple-900">Login</button
			>
		</div>
	</div>
</header>
<main class="container mx-auto pt-20">
	<slot />
</main>

<footer class="h-20 bg-black mt-10 text-white flex justify-center items-center">
	<small>@2022</small>
</footer>
