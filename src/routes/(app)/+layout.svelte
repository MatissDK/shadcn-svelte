<script lang="ts">
	import '../../app.pcss';
	import { ModeWatcher } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button';
	import { Moon, Sun } from 'lucide-svelte';
	import { toggleMode } from 'mode-watcher';
</script>

<ModeWatcher />

<div class="flex min-h-screen flex-col pt-16">

	<header class="fixed background foreground top-0 w-full border-b p-4 shadow-sm">
		<nav class="container mx-auto flex items-center justify-between">
			<!-- Navbar Content -->
			<div>
				<a href="/" class="text-xl font-semibold">shadcn-svelte </a>
			</div>

			<div class="hidden items-center space-x-4 md:flex">
				<a href="/login">
					<Button variant="ghost">
						Sign in
					</Button>
				</a>
				
				<Button on:click={toggleMode} size="icon" variant="ghost">
					<Moon size={20}
						class="rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
					/>
					<Sun size={20}
						class="absolute rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
					/>
				</Button>
			</div>
		</nav>
	</header>

	<div class="container mx-auto flex-grow p-4">
		<slot />
	</div>

	<footer class="p-4 mt-auto border-t shadow-md background foreground">
		<div class="container mx-auto">
			<!-- Footer content goes here -->
			<p>&copy; 2024. All rights reserved.</p>
		</div>
	</footer>
</div>
