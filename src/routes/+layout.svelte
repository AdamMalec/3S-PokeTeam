<script lang="ts">
	import '../app.css';

	import SunIcon from '@lucide/svelte/icons/sun';
	import MoonIcon from '@lucide/svelte/icons/moon';

	import { ModeWatcher, toggleMode  } from 'mode-watcher';
	import { Button } from '$lib/components/ui/button/index.js';
	import { goto } from '$app/navigation';

	let { children } = $props();
</script>

<ModeWatcher />

<header class="header">
	<div class="header__container container">
		<nav class="menu">
			<ul class="menu__list">
				<li><a href="/">Home</a></li>
				<li><a href="/team">Team</a></li>
			</ul>
		</nav>
		<div class="actions">
			<ul class="actions__list">
				<li>user@gmail.com</li>
				<li>
					<Button variant="outline" class="cursor-pointer" onclick={() => goto('/login')}>Sign in</Button></li>
				<li>
					<Button onclick={toggleMode} variant="outline" class="cursor-pointer" size="icon">
						<SunIcon
							class="h-[1.2rem] w-[1.2rem] scale-100 rotate-0 transition-all dark:scale-0 dark:-rotate-90"
						/>
						<MoonIcon
							class="absolute h-[1.2rem] w-[1.2rem] scale-0 rotate-90 transition-all dark:scale-100 dark:rotate-0"
						/>
						<span class="sr-only">Toggle theme</span>
					</Button>
				</li>
			</ul>
		</div>
	</div>
</header>

<main class="container">
	{@render children()}
</main>

<footer></footer>

<style>
	main {
		display: grid;
		place-items: center;
		align-content: center;
		gap: 2rem;
		height: 60vh;
	}
	.header {
		padding: 1rem;
		background-color: var(--secondary);
	}

	.header__container,
	.menu__list,
	.actions__list {
		display: flex;
		justify-content: space-between;
		align-items: center;
		gap: 1rem;
	}
</style>
