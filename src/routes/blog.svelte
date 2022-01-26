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
	export const params = { id: null };
	function getItems() {
		fetch(`https://api.giphy.com/v1/gifs/${params.id}?api_key=0yI0K3PIwzAuwht9P4sGclUJ7UTSwxLv`)
			.then((x) => x.json())
			.then((x) => {
				console.log(x.data);
			})
			.catch((_) => {});
	}
</script>

<h1 class="my-3 text-3xl text-purple-600 font-medium">Images</h1>
<div class="grid grid-flow-col grid-rows-3 md:grid-rows-2 grid-cols-2 md:grid-cols-3 gap-4">
	<div>
		<img
			src="https://images.unsplash.com/photo-1643212673511-687979d063eb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
			alt="Demo 01"
			class="h-96 object-cover rounded-lg hover:shadow-lg hover:shadow-slate-400 transition-shadow cursor-pointer"
		/>
	</div>
	<div>
		<img
			src="https://images.unsplash.com/photo-1606431941858-3b4644719224?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=872&q=80"
			alt="Demo 01"
			class="h-96 object-cover w-full rounded-lg hover:shadow-lg hover:shadow-slate-400 transition-shadow cursor-pointer"
		/>
	</div>
	<div>
		<img
			src="https://images.unsplash.com/photo-1643110867496-4a78323fdc17?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=928&q=80"
			alt="demo 03"
			class="h-96 object-cover w-full rounded-lg hover:shadow-lg hover:shadow-slate-400 transition-shadow cursor-pointer"
		/>
	</div>
	<div>
		<img
			src="https://images.unsplash.com/photo-1643138874737-33babf17f0a8?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1740&q=80"
			alt="Demo 04"
			class="h-96 object-cover w-full rounded-lg hover:shadow-lg hover:shadow-slate-400 transition-shadow cursor-pointer"
		/>
	</div>
	<div class="row-start-1 col-start-1 md:col-start-2 col-span-2 ">
		<img
			src="https://images.unsplash.com/photo-1643136629120-7e4d4378bfb7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2831&q=80 "
			alt="Demo 05"
			class="md:h-96 object-cover h-full w-full rounded-lg hover:shadow-lg hover:shadow-slate-400 transition-shadow cursor-pointer"
		/>
	</div>
</div>
