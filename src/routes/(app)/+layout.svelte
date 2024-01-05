<script lang="ts">
	import '../../app.pcss';
	import Header from '$lib/components/ux/Header.svelte';
	import Footer from '$lib/components/ux/Footer.svelte';
	import Container from "$lib/components/ux/Container.svelte";
	import { ModeWatcher } from 'mode-watcher';
</script>

<ModeWatcher />


<div class="flex min-h-screen flex-col pt-24">

	<Header/>

	<Container>
		<slot />
	</Container>

	<div class="flex-1"></div>

	<Footer/>

</div>
