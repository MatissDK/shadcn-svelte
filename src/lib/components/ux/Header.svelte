<script lang="ts">
	import Container from '$lib/components/ux/Container.svelte';
	import * as Sheet from '$lib/components/ui/sheet';
	import { Button } from '$lib/components/ui/button';
	import { Moon, Sun, Menu } from 'lucide-svelte';
	import { toggleMode } from 'mode-watcher';

	let links = [
		{
			href: '/about',
			label: 'About'
		},
		{
			href: '/terms',
			label: 'Terms'
		}
	];
</script>

<header class="fixed top-0 flex h-20 w-full items-center border-b bg-background py-4">
	<Container>
		<div class="flex items-center justify-between">
			<div class="flex items-center">
				<a href="/">
					<div class="text-xl font-semibold">shadcn-svelte</div>
				</a>
			</div>

			<div class="flex items-center">
				<nav class="hidden md:flex">
					{#each links as link}
						<a href={link.href}>
							<Button variant="ghost">{link.label}</Button>
						</a>
					{/each}
				</nav>
				<Sheet.Root>
					<Sheet.Trigger asChild let:builder>
						<Button builders={[builder]} size="icon" variant="ghost" class="sm:hidden">
							<Menu size={20} />
						</Button>
					</Sheet.Trigger>
					<Sheet.Content side="left">
						<Sheet.Header>
							<!-- <Sheet.Title>Are you sure absolutely sure?</Sheet.Title> -->
							<Sheet.Description>
								<div class="mt-8 flex flex-col">
									{#each links as link}
										<a href={link.href}>
											<Button variant="ghost">{link.label}</Button>
										</a>
									{/each}
                                    <a href="/login" class="mt-8 w-full">
                                        <Button variant="ghost" class="w-full">Sign in</Button>
                                    </a>
								</div>
                                <div class="absolute bottom-0 left-0 w-full pb-8">
                                    <Button on:click={toggleMode} size="icon" variant="ghost">
                                        <Moon size={20} class="rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0" />
                                        <Sun
                                            size={20}
                                            class="absolute rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
                                        />
                                    </Button>
                                </div>
							</Sheet.Description>
						</Sheet.Header>
					</Sheet.Content>
				</Sheet.Root>
			</div>

			<div class="hidden items-center md:flex">
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
	</Container>
</header>
