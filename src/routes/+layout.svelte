<!-- <script lang="ts">
	import '../app.pcss';
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

	<div class="pt-5">
		<Footer/>
	</div>
	

</div> -->


<script lang="ts">
	import '../app.pcss';
	import { ModeWatcher } from 'mode-watcher';
</script>

<ModeWatcher />


<slot/>
<!-- <div class="flex min-h-screen flex-col pt-24">
	<slot/>
</div> -->
