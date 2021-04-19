<script>
	export let value;
    export let onEdit;
    export let edit;
    export let remove;
    export let id;
</script>


<div class='card'>
    <div>
        <input readonly={!onEdit} value = {value}/>
        <button on:click={edit} >Sửa</button>
        <button on:click={remove}>Xóa</button>
    </div>
</div>


<style>
	.card {
		position: relative;
		margin: 0.5em;
		padding: 0.5em 0.5em 0.5em 6em;
		border: 1px solid #eee;
		border-radius: 4px;
		box-shadow: 2px 2px 4px rgba(0,0,0,0.1);
		min-height: 5em;
	}

	.card::after {
		clear: both;
		display: block;
	}
</style>