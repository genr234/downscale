<div class="reflection">
	{@render children()}
</div>

<script lang="ts">
	import type { Snippet } from 'svelte';
	let { children }: { children: Snippet } = $props();
</script>

<style>
	.reflection {
		border: 5px solid var(--color-p-red-2);
		border-top-width: 8px;
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		background: var(--color-p-navy);
	}
</style>
