<script lang="ts">
	import Debugger from 'svelte-debugger';
	import { search } from '../stores/index';
	let list: Giphy[] = [];
	let _search = 'goku';

	search.subscribe((value) => {
		_search = value;
	});
	function getItems() {
		fetch(
			`https://api.giphy.com/v1/gifs/search?api_key=0yI0K3PIwzAuwht9P4sGclUJ7UTSwxLv&q=${_search}&limit=25&offset=0&rating=g&lang=en`
		)
			.then((x) => x.json())
			.then((x) => {
				list = x.data.map((x) => ({
					...x,
					image: x.images.original.url
				}));
			})
			.catch((_) => {});
	}

	getItems();

	$: if (_search) {
		search.update((n) => _search);

		getItems();
	}

	interface Giphy {
		username: string;
		title: string;
		url: string;
		image: string;
		slug: string;
		id: string;
	}
</script>

<svelte:head>
	<title>Welcome</title>
</svelte:head>

<h1 class="text-purple-700 text-2xl font-medium">Welcome to SvelteKit</h1>
<input
	type="text"
	bind:value={_search}
	class="bg-gray-200 rounded-md py-1 px-2 focus:bg-gray-300 focus:outline-0 my-2 w-3/12 placeholder:text-gray-500"
	placeholder="Search"
/>
<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-10 ">
	{#each list as item}
		<a
			href={item.url}
			target="_blank"
			class="shadow-sm nimate-ping shadow-purple-200 bg-white py-2 px-2 rounded-sm hover:shadow-purple-300 hover:shadow-lg transition-shadow cursor-pointer"
		>
			<p class="text-md mb-2 font-thin ">
				{item.title.slice(0, 24) || item.username}{item.title.length > 24 ? '...' : ''}
			</p>
			<div
				class="w-full h-36 backdrop-blur-md bg-no-repeat bg-center"
				style={`background-image:url(${item.image})`}
			/>
			<!-- <img width="100px" src={item.image} alt={item.title} /> -->
			<span class="divide-x-2" />
			<div class="flex justify-center mt-3">
				<a
					href={`/${item.id}`}
					class="bg-purple-600 hover:bg-purple-500 shadow-purple-500 text-white py-2 px-6 rounded-md hover:shadow-md"
					>Go
				</a>
			</div>
		</a>
	{/each}
</div>
<!-- {#if list.length}
	<Debugger
		data={list}
		indent={2}
		colorOptions={{
			falseColor: '#ff3e00',
			trueColor: '#40b3ff',
			keyColor: 'red',
			stringColor: 'orange'
		}}
	/>
{/if} -->
