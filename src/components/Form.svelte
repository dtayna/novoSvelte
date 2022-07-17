<div class="Form">
	<label> Número de Tabs: </label>
	<button on:click={e=> increment()}>{count}</button>
	<br />
	<br />
	<hr />
	{#each quant as q,i}
	<div :key="i">
		<label> Titulo: </label>
		<input bind:value={q} class="texto" on:change={e=>addTitulo(i,q)}
		/>
		<br />
		<label> Conteúdo: </label>
		<textarea bind:value={textvalue[i]} class="textoConteudo" on:change={e=>addConteudo(i,textvalue[i])}
     />
    </div>
    {/each}
     <button class="botao" on:click={e=>submeter()}>Submeter</button>
	<div class="tabs">
  <Tab topos={coisa1} conteudos={coisa2} />
</div>
</div>

<script lang="ts">
  import Tab from "./Tab.svelte";

  let quant = [];
  let count = 0;
  let titulos = [];
  let conteudos = [];
  let coisa1 = [];
  let coisa2 = [];
  let nivel = 0;
  let textvalue = [];

  function increment() {
    quant[count] = count;
    count++;
  }

  function addTitulo(j, comp) {
    titulos[j] = comp;
  }

  function addConteudo(j, comp) {
    conteudos[j] = comp;
  }

  function submeter() {
    nivel = 1;
    coisa1 = titulos;
    coisa2 = conteudos;
  }
</script>

<style>
  .tabs {
    padding: 20px;
    margin: 10px 0;
    border-radius: 10px;
    border: 1px solid #aaa;
    background-color: #4caf50;
    width: 100%;
    height: 300px;
  }
  .textoConteudo {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  .botao {
    width: 50%;
    margin: 25%;
    background-color: #4caf50;
    color: white;
    padding: 14px 20px;
    margin-left: 25%;
    border: none;
    border-radius: 4px;
    cursor: pointer;
  }
  .texto {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    display: inline-block;
    border: 1px solid #ccc;
    border-radius: 4px;
    box-sizing: border-box;
  }
  .principal {
    width: 50%;
  }
</style>