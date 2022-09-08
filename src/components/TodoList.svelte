<script>
    let newItem = '';
	
    let todoList = [{text: 'Créer  un composants réutilisable', status: true},
                    {text: 'Faire le ménage', status: false},
                    {text: 'Faire les courses', status: false}];
	
	function addToList() {
		todoList = [...todoList, {text: newItem, status: false}];
		newItem = '';
	}
	
	function removeFromList(index) {
		todoList.splice(index, 1)
		todoList = todoList;
    }
</script>

<input bind:value={newItem} type="text" placeholder="Nouvelle tâche...">
<button on:click={addToList}>Ajouter</button>

<br/>
{#each todoList as item, index}
	<input bind:checked={item.status} type="checkbox">
	<span class:checked={item.status}>{item.text}</span>
	<span on:click={() => removeFromList(index)}>❌</span>
	<br/>
{/each} 


<style> 
	.checked {
        text-decoration: line-through;
    }
	input{
		background: #f5e99f;
	}
	button {
    max-width: 500px;
    margin: 2rem 0;
    padding: 0.2rem 1.25rem;
    text-align: center;
    font-family: "Dekko", cursive;
    text-transform: uppercase;
    font-size: 1rem;
    letter-spacing: 0.2rem;
    background: url('data:image/svg+xml;utf8,<svg width="100" height="100" transform="rotate(25)" opacity="0.3" version="1.1" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><g  fill="%23250E17"><circle cx="25" cy="25" r="12.5"/><circle cx="75" cy="75" r="12.5"/><circle cx="75" cy="25" r="12.5"/><circle cx="25" cy="75" r="12.5"/></g></svg>'),
      #fff;
    background-size: 12px, 100%;
    border: 0.2rem solid #000;
    border-radius: 0px !important;
    position: relative;
    background-color: #ffcd28;

  }

  button {
    background-size: 13px, 100%;
    font-weight: 700;
    border-radius: 50%;
  }
  button {
    content: "!";
  }
</style> 