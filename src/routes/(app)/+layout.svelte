<script lang="ts">
	import Header from '$lib/components/ux/Header.svelte';
	import Footer from '$lib/components/ux/Footer.svelte';
	import Container from "$lib/components/ux/Container.svelte";
</script>


<div class="flex min-h-screen flex-col pt-24">

	<Header/>

	<Container>
		<slot />
	</Container>

	<div class="flex-1"></div>

	<div class="pt-5">
		<Footer/>
	</div>
	

</div>