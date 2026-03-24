<script lang="ts">
	let { children } = $props();
</script>

<div class="guide-page">
	<div class="guide-container">
		{@render children()}
	</div>
</div>

<style>
	:global(html) {
		background-color: var(--color-p-navy) !important;
	}

	.guide-page {
		background: var(--color-p-navy);
		min-height: 100vh;
		padding: 3rem 1.5rem 6rem;
	}

	.guide-container {
		max-width: 740px;
		margin: 0 auto;
	}

	/* Typography */
	.guide-container :global(h1) {
		font-size: 1.6rem;
		color: var(--color-p-red-1);
		border-bottom: 5px solid var(--color-p-red-1);
		padding-bottom: 0.6rem;
		margin-top: 2.5rem;
		margin-bottom: 1.25rem;
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	.guide-container :global(h2) {
		font-size: 1.2rem;
		color: var(--color-p-red-1);
		border-bottom: 5px solid var(--color-p-red-2);
		padding-bottom: 0.4rem;
		margin-top: 3rem;
		margin-bottom: 1rem;
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	.guide-container :global(h3) {
		font-size: 0.95rem;
		color: var(--color-p-white);
		margin-top: 2rem;
		margin-bottom: 0.75rem;
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	.guide-container :global(p),
	.guide-container :global(ul),
	.guide-container :global(ol) {
		font-size: 0.8rem;
		line-height: 2;
		margin: 1rem 0;
		color: var(--color-p-lightgray);
	}

	.guide-container :global(ul),
	.guide-container :global(ol) {
		padding-left: 1.5rem;
	}

	.guide-container :global(li) {
		margin: 0.4rem 0;
	}

	.guide-container :global(li::marker) {
		color: var(--color-p-red-2);
	}

	.guide-container :global(strong) {
		color: var(--color-p-white);
	}

	.guide-container :global(em) {
		color: var(--color-p-white);
		font-style: italic;
	}

	/* Code */
	.guide-container :global(code) {
		font-family: var(--font-pico);
		color: var(--color-p-red-1);
		font-size: 0.8em;
	}

	.guide-container :global(pre) {
		background: #0a0f1a;
		padding: 1.25rem 1.5rem;
		overflow-x: auto;
		border: 5px solid var(--color-p-red-2);
		margin: 1.5rem 0;
		font-size: 0.75rem;
		line-height: 1.8;
		white-space: pre-wrap;
	}

	.guide-container :global(pre code) {
		color: var(--color-p-lightgray);
		font-size: inherit;
	}

	/* Tables */
	.guide-container :global(table) {
		border-collapse: collapse;
		margin: 1.5rem 0;
		width: 100%;
		font-size: 0.75rem;
	}

	.guide-container :global(td),
	.guide-container :global(th) {
		border: 5px solid var(--color-p-red-2);
		padding: 0.6rem 0.8rem;
		text-align: left;
		color: var(--color-p-lightgray);
	}

	.guide-container :global(th) {
		color: var(--color-p-red-1);
	}

	/* Details/Summary (hints & solutions) */
	.guide-container :global(details) {
		border: 5px solid var(--color-p-navy-light);
		margin: 0.75rem 0;
		background: #0a0f1a;
		transition: border-color 0.2s;
	}

	.guide-container :global(details:hover) {
		border-color: var(--color-p-gray);
	}

	.guide-container :global(details[open]) {
		border-color: var(--color-p-red-2);
	}

	.guide-container :global(details summary) {
		cursor: pointer;
		color: var(--color-p-gray);
		padding: 0.8rem 1.25rem;
		font-size: 0.8rem;
		user-select: none;
		transition: color 0.2s;
	}

	.guide-container :global(details:hover summary) {
		color: var(--color-p-lightgray);
	}

	.guide-container :global(details[open] summary) {
		color: var(--color-p-red-1);
		margin-bottom: 0;
		border-bottom: 5px solid var(--color-p-red-2);
	}

	.guide-container :global(details > :not(summary)) {
		padding: 0 1.25rem;
	}

	.guide-container :global(details > p:last-child),
	.guide-container :global(details > pre:last-child) {
		margin-bottom: 1rem;
	}

	/* Horizontal rules */
	.guide-container :global(hr) {
		border: none;
		border-top: 5px solid var(--color-p-red-2);
		margin: 3.5rem 0;
	}

	/* Links */
	.guide-container :global(a) {
		color: var(--color-p-red-1);
		text-decoration: none;
	}

	.guide-container :global(a:hover) {
		text-decoration: underline;
		text-underline-offset: 5px;
		text-decoration-thickness: 3px;
	}

	/* Images */
	.guide-container :global(img) {
		max-width: 100%;
		margin: 1.5rem 0;
		border: 5px solid var(--color-p-red-2);
	}
</style>
