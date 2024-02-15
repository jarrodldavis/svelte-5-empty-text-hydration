<script>
    import { onMount } from "svelte";

    /** @type {HTMLDivElement | undefined} */
    let wrapper = $state();

    const lines = $state(['first', 'second', '', 'fourth']);

    function update_lines() {
        lines[0] = 'first, updated'
        lines[2] = 'third'
    }

    onMount(() => {
        // appease typescript
        if (!wrapper) {
            return;
        }

        // Two nodes, as expected (text, and `<br>`)
        const first_line = wrapper.children[0];
        console.log('first line nodes:', first_line.childNodes);

        // Only one node, since the text node doesn't exist for an empty string
        const third_line = wrapper.children[2];
        console.log('third line nodes:', third_line.childNodes);
    })
</script>

<div bind:this={wrapper}>
    {#each lines as line}
        <div>{line}<br></div>
    {/each}
</div>

<button on:click={update_lines}>Update First and Third Lines</button>
