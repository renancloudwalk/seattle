<script> import { fade } from 'svelte/transition';
	export let objAttributes = {};
</script>
<li transition:fade>
    eu sou a forma:
	{objAttributes.name} ____id={objAttributes.id}____
</li>
