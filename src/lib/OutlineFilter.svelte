<script lang="ts">
    export let twColor = "--color-p-navy";
    export let radius = 5;
    export let style: string = "";

    const id = `outline-filter-${Math.random().toString(36).substring(2, 15)}`;
</script>

<svg width="0" height="0" style="position: absolute;">
    <defs>
        <filter {id} x="-20%" y="-20%" width="140%" height="140%">
            <feMorphology in="SourceAlpha" operator="dilate" radius={radius} result="dilated" />
            <feFlood flood-color="var({twColor})" result="color" />
            <feComposite in="color" in2="dilated" operator="in" result="outline" />
            <feMerge>
                <feMergeNode in="outline" />
                <feMergeNode in="SourceGraphic" />
            </feMerge>
        </filter>
    </defs>
</svg>

<span style="filter: url(#{id}); {style}">
    <slot />
</span>
