<script>
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'

    import Roller from './lib/Roller.svelte'
  import Celeb from './lib/Celeb.svelte'
  let celebA_feet = 5;
  let celebA_inches = 10;
  let celebA_gender = 'M'
  let celebB_feet = 5;
  let celebB_inches = 7;
  let celebB_gender = 'M'
  	function handleMessage(event) {
      console.log(event.detail)
      if(event.detail.v == 'celebA'){
        celebA_feet = event.detail.height.feet
        celebA_inches = event.detail.height.inches
        celebA_gender = event.detail.gender.gender
      }else{
        celebB_feet = event.detail.height.feet
        celebB_inches = event.detail.height.inches
        celebB_gender = event.detail.gender.gender
      }
		
	}
</script>

<main>


  <div class="card" >
 
  <div class="stage">
  <div>
   
   <Celeb feet={celebA_feet} inches={celebA_inches} gender={celebA_gender}/>
   <Roller on:message={handleMessage} v={'celebA'} />
  </div>
     <div>
     
      <Celeb feet={celebB_feet} inches={celebB_inches} gender={celebB_gender}  />
      <Roller on:message={handleMessage} v={'celebB'} />
     </div>
    
  </div>
 
  </div>


</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
