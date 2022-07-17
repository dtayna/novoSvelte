<div class="Tab">
	{#each topos as topo, i}
	<button class="botoes" {topo} on:click={e=> onSelection(i)}>
		{topo}
	</button>
	{/each}
	<div class="corpos">
		{conteudos[tabS]}
	</div>
</div>


<script lang="ts">
	export let conteudos = [];
	export let topos = [];
	let tabS = 0;

	let currentCont = 0;

	function onSelection(x) {
	  tabS = x;
	}
</script>

<style>
  .botoes {
    margin: 20px;
    width: 50px;
  }

  .corpos {
    padding-left: 10px;
    width: 92%;
    height: 200px;
    margin-left: 3%;
    margin-top: 5%;
    border-top: 5px solid green;
    background-color: #98fb98;
  }
</style>