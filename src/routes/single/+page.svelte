<script>
    let text = $state('');

    function update_text() {
        text = 'updated';
    }
</script>

<button type="button" on:click={update_text}>Update Text</button>

<p>
    Dynamic Text and <code>&lt;br&gt;</code> inside <code>&lt;div&gt;</code>:
</p>
<div>{text}<br /></div>

<p>
    Static + Dynamic Text and <code>&lt;br&gt;</code> inside <code>&lt;div&gt;</code>:
</p>
<div>
    Text:{text}<br />
</div>

<style>
    div {
        border: 1px solid red;
    }
</style>
