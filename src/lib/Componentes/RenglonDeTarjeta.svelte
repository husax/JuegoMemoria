<script>
	import Tarjeta from "./Tarjeta.svelte";
	let {renglonDeCadenas }= $props();  // define renglonDeCadenas como un atributo
	console.log(renglonDeCadenas);
	let primerBoton= $state(null); // permite que el componente padre controle el estado del primer clic
</script>

{#each renglonDeCadenas as cadena	}
	<!-- Aquí se itera sobre cada cadena en el arreglo renglonDeCadenas -->
	<!-- y se crea una Tarjeta para cada una -->
	<Tarjeta propCadena = {cadena} {primerBoton}/>
{/each}


<!-- 
<Tarjeta propCadena = {renglonDeCadenas[0]}/>
<Tarjeta propCadena = {renglonDeCadenas[1]}/>
<Tarjeta propCadena = {renglonDeCadenas[2]}/>
<Tarjeta propCadena = {renglonDeCadenas[3]}/>
<Tarjeta propCadena = {renglonDeCadenas[4]}/> -->