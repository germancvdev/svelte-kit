<script context="module">
	export function load({ params }) {
		return {
			props: {
				params: params
			}
		};
	}
</script>

<script lang="ts">
	import Debugger from 'svelte-debugger';

	export let params;
	console.log(params);
	let item = null;
	getItems();
	function getItems() {
		fetch(`https://api.giphy.com/v1/gifs/${params.id}?api_key=0yI0K3PIwzAuwht9P4sGclUJ7UTSwxLv`)
			.then((x) => x.json())
			.then((x) => {
				item = x.data;
			})
			.catch((_) => {});
	}
</script>

<div class="w-6/12 mx-auto">
	{#if item != null}
		<h1 class="text-2xl py-3 text-purple-700 font-medium text-center">{item.title || ''}</h1>
		<img src={item.images.original.url} alt={item.title} class="mb-3 text-center mx-auto" />
		<div class="text-center py-4">
			<a href="/" class="bg-purple-600 py-3 px-4 text-white rounded-lg hover:bg-purple-500">Back</a>
		</div>
	{/if}
</div>
<!-- {#if item != null}
	<Debugger
		data={item}
		indent={2}
		colorOptions={{
			falseColor: '#ff3e00',
			trueColor: '#40b3ff',
			keyColor: 'red',
			stringColor: 'orange'
		}}
	/>
{/if} -->
