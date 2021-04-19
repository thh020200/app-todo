<script>
    import List from './List.svelte' 
	export let value = '';
    export let tasks = [];
    let id = 0;
    let onEdit = false;
    function handleClick() {
        tasks.push({ id: id++, value: value });
        tasks = tasks;
        value = '';
	}

    
    export function handleEditClick() {
        onEdit = true;
	}

    export function handleDeleteClick(index) {
        tasks = [
			...tasks.slice(0, index),
			...tasks.slice(index + 1, tasks.length)
		];
	}
</script>

<input bind:value={value}>

<button on:click={handleClick}>
	Add
</button>
{#each tasks as task, index (task.id)}
    <List {tasks}
    id = {task.id}
    value = {task.value}
    onEdit = {onEdit}
    edit={handleEditClick}
    remove={()=>handleDeleteClick(index)}/>
{/each}


