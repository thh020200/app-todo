<script>
	let value = '';

    function handleClick() {
		alert(value)
	}
</script>

<input bind:value={value}>

<button on:click={handleClick}>
	Add
</button>