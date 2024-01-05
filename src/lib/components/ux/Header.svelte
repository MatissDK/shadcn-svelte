<script lang="ts">
	import Container from '$lib/components/ux/Container.svelte';
	import * as Sheet from '$lib/components/ui/sheet';
	import { Button } from '$lib/components/ui/button';
	import { Moon, Sun, Menu } from 'lucide-svelte';
	import { toggleMode } from 'mode-watcher';
</script>

<header class="background foreground fixed top-0 flex h-20 w-full items-center border-b py-4">
	<Container>
		<div class="flex items-center justify-between">
			<div class="flex items-center">
				<Sheet.Root>
					<Sheet.Trigger>
						<Button size="icon" variant="ghost" class="sm:hidden">
							<Menu size={20} />
						</Button>
					</Sheet.Trigger>
					<Sheet.Content side="left">
						<Sheet.Header>
							<Sheet.Title>Are you sure absolutely sure?</Sheet.Title>
							<Sheet.Description>
								This action cannot be undone. This will permanently delete your account and remove
								your data from our servers.
							</Sheet.Description>
						</Sheet.Header>
					</Sheet.Content>
				</Sheet.Root>

				<a href="/" class="ml-2 sm:ml-0">
					<div class="text-xl font-semibold">shadcn-svelte</div>
				</a>
			</div>

			<div class="flex items-center">
				<a href="/login">
					<Button variant="ghost">Sign in</Button>
				</a>

				<Button on:click={toggleMode} size="icon" variant="ghost">
					<Moon size={20} class="rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
					<Sun
						size={20}
						class="absolute rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
					/>
				</Button>
			</div>
		</div>

		<!-- <Sheet.Root>
				<Sheet.Trigger>
					<Button size="icon" variant="ghost" class="sm:hidden">
						<Menu size={20} />
					</Button>
				</Sheet.Trigger>
				<Sheet.Content side="left">
					<Sheet.Header>
						<Sheet.Title>Are you sure absolutely sure?</Sheet.Title>
						<Sheet.Description>
							This action cannot be undone. This will permanently delete your account and remove
							your data from our servers.
						</Sheet.Description>
					</Sheet.Header>
				</Sheet.Content>
			</Sheet.Root> -->

		<!-- <div class="items-center space-x-4 flex border">
				<Button variant="ghost">
					<a href="/login"> Sign in</a>
				</Button>

				<Button on:click={toggleMode} size="icon" variant="ghost">
					<Moon size={20} class="rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
					<Sun
						size={20}
						class="absolute rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
					/>
				</Button>
			</div> -->
	</Container>
</header>
