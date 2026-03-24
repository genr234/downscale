<div class="challenge">
	{@render children()}
</div>

<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<style>
	.challenge {
		border: 3px solid var(--color-p-navy-light);
		border-left: 3px solid var(--color-p-red-2);
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		background: var(--color-p-navy-light);
		color: var(--color-p-lightgray);
	}
</style>
