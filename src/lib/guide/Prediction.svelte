<div class="prediction">
	{@render children()}
</div>

<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<style>
	.prediction {
		border: 3px dashed var(--color-p-gray);
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		background: var(--color-p-navy-light);
		color: var(--color-p-lightgray);
	}
</style>
