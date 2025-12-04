<script lang="ts">
	import ShinyText from "$lib/ShinyText.svelte";
	import Particles from "$lib/Particles.svelte";
	import OutlineFilter from "$lib/OutlineFilter.svelte";
	import ShinyTitle from "$lib/ShinyTitle.svelte";
</script>

<div class="relative min-h-[calc(100vh-20px)] w-screen bg-p-navy overflow-hidden">
	<Particles density={20} maxSpeed={3} />
	<Particles density={3} minSpeed={2} maxSpeed={4} z={1} twColor="--color-p-gray" />
	<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2">
		<div class="relative mb-16 w-max mx-auto">
			<img
				src="/mountain.png"
				alt=""
				class="absolute top-1/2 left-1/2 -z-1 w-[375px] -translate-x-[calc(50%-10px)] -translate-y-[calc(50%+11px)] select-none"
				draggable="false"
			/>
            <!-- TODO: animate -->
            <p class="text-transparent selection:bg-p-red-1 font-title text-p8-title absolute left-1/2 -translate-x-1/2 top-1/2 -translate-y-1/2">
                downscale
            </p>
			<OutlineFilter style="pointer-events: none; user-select: none;">
                <img src="/downscale-plain.png" alt="downscale" class="w-[415px]"/>
            </OutlineFilter>
            <!-- <img src="/downscale.png" alt="downscale" class="w-[425px] select-none" draggable="false" /> -->
		</div>
        <!-- <div class="px-1"> -->
        <div class="w-max mx-auto">
            <p>
                <ShinyText c1="var(--color-p-white)" c2="var(--color-p-lightgray)">
                    Make a retro game with
                </ShinyText>
                <ShinyText c1="var(--color-p-red-1)" c2="var(--color-p-red-2)">
                    PICO-8
                </ShinyText>
            </p>
            <div class="mt-4 w-max leading-9.5 mx-auto">
                <ShinyText c1="var(--color-p-white)" c2="var(--color-p-lightgray)">
                    Get a
                </ShinyText>
                <ShinyText c1="var(--color-p-red-1)" c2="var(--color-p-red-2)">
                    PICO-8 LICENSE
                </ShinyText>
                <br>
                <ShinyText c1="var(--color-p-red-2)" c2="var(--color-p-red-3)" style="text-align: right; display: inline-block; width: 100%;">
                    + CUSTOM STICKER
                </ShinyText>
                <br>
                <ShinyText c1="var(--color-p-red-2)" c2="var(--color-p-red-3)" style="text-align: right; display: inline-block; width: 100%;">
                    + STEAM GIFTCARD
                </ShinyText>
            </div>
        </div>
	</div>
</div>

<!-- <div class="w-screen h-[225px] absolute z-2 -translate-y-[10vh] bg-[url(/mountains-loop.png)] bg-size-[auto_225px] bg-repeat-x"></div> -->

<img src="/down.png" alt="Scroll Down" class="w-[25px] absolute left-1/2 -translate-x-1/2 -translate-y-[12vh]">

<div class="bg-p-red-1 h-[20px] relative z-2">
    <div class="w-screen h-[40px] -translate-y-full bg-[url(/divider-tile.png)] bg-size-[auto_100%] bg-repeat-x animate-move-bg"></div>
</div>

<div class="min-h-screen bg-p-red-1 px-12 max-sm:px-4">
    
    <h1 class="text-p8-title leading-p8-title font-title pt-8 text-center -mb-[25px] relative z-1">
        <OutlineFilter>
            <ShinyTitle c1="var(--color-p-white)" c2="var(--color-p-lightgray)">
                what is this?
            </ShinyTitle>
        </OutlineFilter>
    </h1>

    <div class="bg-p-navy max-w-4xl mx-auto pt-10 pb-8 px-12 max-sm:px-6 relative z-0">        
        <p class="text-p8 text-white">
            <!-- <ShinyText c1="var(--color-p-red-1)" c2="var(--color-p-red-2)" style="display: inline;">
                <span class="relative before:absolute before:top-0 before:left-0 before:w-[calc(100%-5px)] before:h-[calc(100%-2.5px)] before:bg-p-navy-light before:-z-1">
                    DOWNSCALE
                </span>
            </ShinyText> -->

            downscale
            
            is a <a href="https://hackclub.com" class="underline-p8 [--underline-color:var(--color-p-gray)] hover:bg-p-red-1" target="_blank">Hack Club</a> <img src="/new-tab.png" alt="" class="h-[30px] inline -ml-3"> program about making retro games with 
        </p>
    </div>
    <p class="text-p8 text-p-white">
        What is PICO-8?
        Well, what's a fantasy console then?
        Why limit yourself?
        Who is this for?
        teenagers who are interested in gamedev + beginners and any skill level 
        What can I get?
        this is for people who enjoy making for the sake of making something cool-- the prizes are awesome but you should do it because it's fun!
        How do I start?
    </p>
    
</div>

<!-- <div class="bg-p-red-1 relative z-2">
    <div class="w-screen h-[100px] -translate-y-[65px] bg-[url(/divider-tentacles.png)] bg-size-[auto_100%] bg-repeat-x"></div>
</div> -->

<style>
	:global(*) {
		image-rendering: pixelated;
	}
    :global(body) {
        background-color: var(--color-p-navy);
    }

    .animate-move-bg {
        /* animation: move-bg 5s steps(10) infinite; */
        animation: move-bg 8s linear infinite;
    }
    @keyframes move-bg {
        from {
            background-position: 0 0;
        }
        to {
            background-position: var(--bg-width, 50px) 0;
        }
    }
</style>


