<script>
import { createEventDispatcher } from 'svelte';
import { heights } from '../heights';
export let search = "";
export let n = [];
export let v;
	const dispatch = createEventDispatcher();
	let selected = "";
	function nameClicked(name) {
		selected = name
		dispatch('message', {
			text: name,
      height: names[name],
			v: v,
			gender: names[name]
		});
	}
  let names = heights;
	let window = 100000;
	 n = Object.keys(names);
	 n.sort()
	let limited = n;
</script>
<h3>{selected}</h3>
<div class="container">
<input placeholder="Search Here" bind:value={search} class="search" type="text" on:keyup={()=>{limited = n.filter((x)=>{return x.toLowerCase().includes(search.toLowerCase())})}} />
<div class="roller-container">

<div class="roller">

		{#each limited.slice(0, window) as name}
			<div class="name {name == selected ? 'selected' : ''} " on:click={()=>{nameClicked(name)}}>{name}</div>
    
			{/each}

</div>
</div>

</div>


	