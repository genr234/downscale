<script lang="ts">
	import { onMount } from "svelte";

	// this is admittedly pretty heavily vibecoded

	interface Props {
		density?: number;
		minSpeed?: number;
		maxSpeed?: number;
		z?: number;
		twColor?: string;
	}

	let { density = 50, minSpeed = 0.25, maxSpeed = 5.25, z = 0, twColor = "--color-p-navy-light" }: Props = $props();

	const SCALE = 5;

	interface Particle {
		x: number;
		y: number;
		s: number;
		spd: number;
		off: number;
	}

	let canvas: HTMLCanvasElement;
	let ctx: CanvasRenderingContext2D;
	let particles: Particle[] = [];
	let animationId: number;
	let logicalWidth = 0;
	let logicalHeight = 0;

	function createParticle(randomY = true): Particle {
		return {
			x: Math.random() * logicalWidth,
			y: randomY ? Math.random() * logicalHeight : -4,
			s: Math.floor((Math.random() * 5) / 4),
			spd: minSpeed + Math.random() * (maxSpeed - minSpeed),
			off: Math.random(),
		};
	}

	function picoSin(x: number): number {
		return -Math.sin(x * Math.PI * 2);
	}

	function update() {
		if (!ctx) return;

		ctx.clearRect(0, 0, logicalWidth, logicalHeight);

		const color = getComputedStyle(canvas).getPropertyValue(twColor).trim();
		ctx.fillStyle = color || "#1d2b53";

		for (const p of particles) {
			p.y += p.spd;
			p.x += picoSin(p.off);
			p.off += Math.min(0.05, p.spd / 32);

			const size = p.s + 1;
			ctx.fillRect(Math.floor(p.x), Math.floor(p.y), size, size);

			if (p.y > logicalHeight + 4) {
				p.y = -4;
				p.x = Math.random() * logicalWidth;
			}
		}

		animationId = requestAnimationFrame(update);
	}

	function resize() {
		if (!canvas) return;
		logicalWidth = Math.ceil(canvas.clientWidth / SCALE);
		logicalHeight = Math.ceil(canvas.clientHeight / SCALE);
		canvas.width = logicalWidth;
		canvas.height = logicalHeight;

		const particleCount = Math.floor(((logicalWidth * logicalHeight) / (128 * 128)) * density);
		particles = Array.from({ length: particleCount }, () => createParticle(true));
	}

	onMount(() => {
		ctx = canvas.getContext("2d")!;
		ctx.imageSmoothingEnabled = false;

		resize();
		update();

		window.addEventListener("resize", resize);

		return () => {
			cancelAnimationFrame(animationId);
			window.removeEventListener("resize", resize);
		};
	});
</script>

<canvas bind:this={canvas} class="pointer-events-none absolute inset-0 h-full w-full" style="z-index: {z};"></canvas>

<style>
	canvas {
		image-rendering: pixelated;
	}
</style>
