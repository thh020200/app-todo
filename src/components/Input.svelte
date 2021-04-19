<script>
    import List from './List.svelte' 
	export let value = '';
    let tasks = [];
    function handleClick() {
        tasks.push(value);
        tasks = tasks;
        value = '';
	}
</script>

<input bind:value={value}>

<button on:click={handleClick}>
	Add
</button>
<List {tasks}/>