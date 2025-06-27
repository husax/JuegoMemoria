<script>
	import Tarjeta from "./Tarjeta.svelte";
	let {renglonDeCadenas, primerBoton=$bindable() }= $props();  // define renglonDeCadenas como un atributo
	console.log(renglonDeCadenas);
	let card= $state(); // Variable para almacenar la referencia al componente Tarjeta
	function asociaTarjeta (){
		primerBoton = card; // Asigna la tarjeta actual como primer botón
	}

</script>

{#each renglonDeCadenas as cadena	}
	<!-- Aquí se itera sobre cada cadena en el arreglo renglonDeCadenas -->
	<!-- y se crea una Tarjeta para cada una -->
	<Tarjeta bind:this={card}  propCadena = {cadena}
		bind:primerBoton={primerBoton} {asociaTarjeta}
		/>
{/each}


<!-- 
<Tarjeta propCadena = {renglonDeCadenas[0]}/>
<Tarjeta propCadena = {renglonDeCadenas[1]}/>
<Tarjeta propCadena = {renglonDeCadenas[2]}/>
<Tarjeta propCadena = {renglonDeCadenas[3]}/>
<Tarjeta propCadena = {renglonDeCadenas[4]}/> -->