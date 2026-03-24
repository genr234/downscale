<script lang="ts">
	let { content }: { content: string } = $props();
</script>

<div class="diagram">{content}</div>

<style>
	.diagram {
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		border: 5px solid var(--color-p-red-2);
		background: var(--color-p-navy);
		white-space: pre;
		font-size: 0.8em;
		line-height: 1.6;
		overflow-x: auto;
	}
</style>
