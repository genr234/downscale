<script lang="ts">
	let { content }: { content: string } = $props();
</script>

<div class="diagram">{content}</div>

<style>
	.diagram {
		padding: 1.25rem 1.5rem;
		margin: 1.5rem 0;
		border: 3px solid var(--color-p-navy-light);
		background: var(--color-p-navy-light);
		color: var(--color-p-lightgray);
		white-space: pre;
		font-family: var(--font-pico);
		font-size: 0.9rem;
		line-height: 1.6;
		overflow-x: auto;
	}
</style>
