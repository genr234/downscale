<script lang="ts">
    export let twColor = "--color-p-navy-light";
</script>

<span style="
    text-shadow:
        -5px -5px 0 var({twColor}),
         0px -5px 0 var({twColor}),
         5px -5px 0 var({twColor}),
        -5px  0px 0 var({twColor}),
         5px  0px 0 var({twColor}),
        -5px  5px 0 var({twColor}),
         0px  5px 0 var({twColor}),
         5px  5px 0 var({twColor});
">
    <slot />
</span>