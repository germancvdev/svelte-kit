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

<h1>Blog</h1>
