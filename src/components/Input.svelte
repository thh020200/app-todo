<script>
    import List from './List.svelte' 
	export let valueInput = '';
    export let tasks = [];
    let id = 0; //id tăng dần

    //Thêm vào list
    function handleAddClick(value) {
        tasks.push({ id: id++, value: value, isEdit:false});
        tasks = tasks;
        valueInput = '';
	}

    //Edit list
    export function handleEditClick(index) {
        tasks[index].isEdit = (tasks[index].isEdit == false)?true:false;
	}

    //Xóa list tại vị trí index
    export function handleDeleteClick(index) {
        tasks = [
			...tasks.slice(0, index),
			...tasks.slice(index + 1, tasks.length)
		];
	}
</script>

<input bind:value={valueInput}>
&nbsp;&nbsp;&nbsp;&nbsp;
<button on:click={()=>handleAddClick(valueInput)}>Add</button>
{#each tasks as task, index (task.id)}
    <List {tasks}
    id = {task.id}
    isEdit = {task.isEdit}
    bind:taskValue = {task.value}
    edit={()=>handleEditClick(index)}
    remove={()=>handleDeleteClick(index)}/>
{/each}
