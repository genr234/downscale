<div class="experiment">
	{@render children()}
</div>

<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<style>
	.experiment {
		border: 5px dotted var(--color-p-lightgray);
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		background: var(--color-p-navy);
	}
</style>
