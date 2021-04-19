<script>
	export let taskValue;
    export let edit;
    export let remove;
    export let isEdit;
</script>

<div class='card'>
    <div>
        {#if isEdit==false}
            {taskValue}
            &nbsp;&nbsp;&nbsp;&nbsp;
            <button on:click={edit}>Edit</button>
        {:else}
            <input bind:value = {taskValue}/>
            &nbsp;&nbsp;&nbsp;&nbsp;
            <button on:click={edit}>Save</button>
        {/if}
        <button on:click={remove}>Xóa</button>
    </div>
</div>

<style>
	.card {
		position: relative;
		margin: 0.5em 0.5em 0.5em 0.5em;
		padding: 0.5em 0.5em 0.5em 0.5em;
		border: 1px solid #eee;
	}
</style>