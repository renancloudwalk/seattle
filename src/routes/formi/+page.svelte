<script>
    import mermaid from 'mermaid';
    import { onMount } from 'svelte';

    let graph = null;

    mermaid.initialize({
        startOnLoad: false,

        theme: 'forest',
    });

	let numbers = [1, 2, 3, 4];

	function addNumber() {
		numbers = [...numbers, numbers.length + 1];
        // mermaid.init([ graph ]);

        const insertSvg = function (svgCode) {
            graph.innerHTML = svgCode;
        };

        const id = 'theGraph';
        const txt = `graph LR\n ${numbers.join(' --> ')}`;

        mermaid.mermaidAPI.render(id, txt, insertSvg, graph);

    }

 $: sum = numbers.reduce((t, n) => t + n, 0);
</script>


<button on:click={addNumber}>
    Add a number
</button>

<main>
    <pre bind:this={graph}>
graph LR

    </pre>
</main>
