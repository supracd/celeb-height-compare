<script>
import logo from '/vite.svg'
import Woman from '../assets/Woman.svelte'
import Man from '../assets/Man.svelte'
export let feet = 0;
export let inches = 0;
export let gender = 'M';
</script>
<div class="celeb">


<div class="celeb-img" style=" height: {((feet * 12) + parseFloat(inches)) * 5}px;">

<div class="celeb-inner" style="height: 100%;{gender == 'M' ? 'opacity: 1;' : 'opacity: 0;height: 0%;'}">
<Man />
</div>
<div class="celeb-inner" style="{gender == 'M' ? 'opacity: 0;height: 0%;' : 'opacity: 1;height: 100%;'}">
<Woman />
</div>
</div>

<div class="holder">
<div class="row">

<input class="size" bind:value={feet} /><label>Feet</label>
</div>
<div class="row">
<input  class="size" bind:value={inches} /><label>Inches</label>
</div>
</div>

</div>
