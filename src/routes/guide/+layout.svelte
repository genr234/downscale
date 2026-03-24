<script lang="ts">
	let { children } = $props();
</script>

<svelte:head>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link href="https://fonts.googleapis.com/css2?family=Jost:wght@400;500;600;700&display=swap" rel="stylesheet" />
</svelte:head>

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
		--px: 3px;
		--guide-red-outline: #422136;
		background: var(--color-p-navy);
		min-height: 100vh;
		padding: 3rem 1.5rem 6rem;
		font-family: 'Jost', sans-serif;
		color: var(--color-p-lightgray);
	}

	.guide-container {
		max-width: 740px;
		margin: 0 auto;
	}

	/*
	   Elevation model (dark mode):
	     Base page:   #111d35  (--color-p-navy)
	     Elevated:    #1d2b53  (--color-p-navy-light)
	     Code inset:  #111d35  (same as page, appears inset inside elevated cards)

	   Border philosophy:
	     3px = proportional to body text size (pixel-art "1px" at this scale)
	     Structural borders: --color-p-navy-light or --color-p-gray
	     Red reserved for meaningful accents only

	   Two-color split gradient (from main page):
	     Headers use background-clip: text with a hard color split
	     PICO-8 font: 36% split, Absolute font: 55.75% split
	*/

	/* ── Headers ── */

	.guide-container :global(h1) {
		display: block;
		border-bottom: 3px solid var(--color-p-navy-light);
		padding-bottom: 1.5rem;
		margin-top: 2.5rem;
		margin-bottom: 1.25rem;
		overflow: visible;
	}

	.guide-container :global(.guide-title) {
		font-family: var(--font-title);
		font-size: var(--text-p8-title);
		line-height: var(--leading-p8-title);
		background-image: linear-gradient(to bottom, var(--color-p-red-1) 55.75%, var(--color-p-red-2) 55.75%);
		-webkit-background-clip: text;
		background-clip: text;
		-webkit-text-fill-color: transparent;
		-webkit-box-decoration-break: clone;
		box-decoration-break: clone;
		text-transform: lowercase;
		letter-spacing: 1px;
	}

	.guide-container :global(.guide-title-white) {
		background-image: linear-gradient(to bottom, var(--color-p-white) 55.75%, var(--color-p-lightgray) 55.75%);
	}

	.guide-container :global(h2) {
		font-family: var(--font-pico);
		font-size: 1.2rem;
		background: linear-gradient(to bottom, var(--color-p-red-1) 36%, var(--color-p-red-2) 36%);
		background-origin: content-box;
		-webkit-background-clip: text;
		background-clip: text;
		-webkit-text-fill-color: transparent;
		border-bottom: 3px solid var(--color-p-navy-light);
		padding-bottom: 0.4rem;
		margin-top: 3rem;
		margin-bottom: 1rem;
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	.guide-container :global(h3) {
		font-family: var(--font-pico);
		font-size: 1.2rem;
		background: linear-gradient(to bottom, var(--color-p-white) 36%, var(--color-p-lightgray) 36%);
		-webkit-background-clip: text;
		background-clip: text;
		-webkit-text-fill-color: transparent;
		margin-top: 2rem;
		margin-bottom: 0.75rem;
		text-transform: uppercase;
		letter-spacing: 1px;
	}

	/* ── Body text ── */

	.guide-container :global(p),
	.guide-container :global(ul),
	.guide-container :global(ol) {
		font-size: 18px;
		line-height: 160%;
		margin: 1rem 0;
		color: var(--color-p-lightgray);
	}

	.guide-container :global(ul),
	.guide-container :global(ol) {
		padding-left: 1.5rem;
	}

	.guide-container :global(ul) {
		list-style: none;
	}

	.guide-container :global(ul > li) {
		position: relative;
		padding-left: 1rem;
	}

	.guide-container :global(ul > li::before) {
		content: '';
		position: absolute;
		left: 0;
		top: 0.65em;
		width: calc(var(--px) * 2);
		height: calc(var(--px) * 2);
		background: var(--color-p-gray);
	}

	.guide-container :global(ol) {
		list-style-type: decimal;
	}

	.guide-container :global(li) {
		margin: 0.6rem 0;
	}

	.guide-container :global(ol > li::marker) {
		color: var(--color-p-gray);
	}

	.guide-container :global(strong) {
		color: var(--color-p-white);
		font-weight: 600;
	}

	.guide-container :global(em) {
		color: var(--color-p-white);
		font-style: italic;
	}

	/* ── Code ── */

	.guide-container :global(code) {
		font-family: var(--font-pico);
		color: var(--color-p-red-1);
		font-size: 0.9rem;
	}

	.guide-container :global(pre) {
		background: var(--color-p-navy);
		padding: 1.25rem 1.5rem;
		overflow-x: auto;
		border: 3px solid var(--color-p-navy-light);
		margin: 1.5rem 0;
		font-size: 0.9rem;
		line-height: 1.8;
		white-space: pre-wrap;
	}

	.guide-container :global(pre code) {
		color: var(--color-p-lightgray);
		font-size: inherit;
	}

	/* ── Tables ── */

	.guide-container :global(table) {
		border-collapse: collapse;
		margin: 1.5rem 0;
		width: 100%;
		font-size: 18px;
	}

	.guide-container :global(td),
	.guide-container :global(th) {
		border: 3px solid var(--color-p-navy-light);
		padding: 0.6rem 0.8rem;
		text-align: left;
		color: var(--color-p-lightgray);
	}

	.guide-container :global(td code) {
		font-size: 0.9rem;
	}

	.guide-container :global(th) {
		color: var(--color-p-white);
		font-weight: 600;
	}

	/* ── Details/Summary (hints & solutions) ── */

	.guide-container :global(details) {
		border: 3px solid var(--color-p-navy-light);
		margin: 0.75rem 0;
		background: var(--color-p-navy-light);
		transition: border-color 0.15s steps(1);
	}

	.guide-container :global(details:hover) {
		border-color: var(--color-p-gray);
	}

	.guide-container :global(details[open]) {
		border-color: var(--color-p-gray);
	}

	.guide-container :global(details summary) {
		cursor: pointer;
		color: var(--color-p-gray);
		padding: 0.8rem 1.25rem;
		font-family: var(--font-pico);
		font-size: 0.9rem;
		user-select: none;
		transition: color 0.15s steps(1);
	}

	.guide-container :global(details:hover summary) {
		color: var(--color-p-lightgray);
	}

	.guide-container :global(details[open] summary) {
		color: var(--color-p-white);
		margin-bottom: 0;
		border-bottom: 3px solid var(--color-p-gray);
	}

	.guide-container :global(details > :not(summary)) {
		padding: 0 1.25rem;
	}

	.guide-container :global(details > p:last-child),
	.guide-container :global(details > pre:last-child) {
		margin-bottom: 1rem;
	}

	/* Code blocks inside details: inset (page-bg color) */
	.guide-container :global(details pre) {
		background: var(--color-p-navy);
	}

	/* ── Horizontal rules ── */

	.guide-container :global(hr) {
		border: none;
		height: var(--px);
		background: var(--color-p-navy-light);
		margin: 3.5rem 0;
	}

	/* ── Links ── */

	.guide-container :global(a) {
		color: var(--color-p-red-1);
		text-decoration: none;
	}

	.guide-container :global(a:hover) {
		text-decoration: underline;
		text-underline-offset: 5px;
		text-decoration-thickness: 3px;
	}

	/* ── Images ── */

	.guide-container :global(img) {
		max-width: 100%;
		margin: 1.5rem 0;
		border: 3px solid var(--color-p-navy-light);
	}
</style>
