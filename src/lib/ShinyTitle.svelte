<script lang="ts">
    export let c1 = "var(--color-p-white)";
    export let c2 = "var(--color-p-lightgray)";
    export let style = "";
</script>

<span id="shiny-text" class="text-p8-title font-title w-max text-transparent bg-clip-text" style={`background-image: linear-gradient(to bottom, ${c1} 55.75%, ${c2} 55.75%); ${style}`}>
    <slot />
</span>