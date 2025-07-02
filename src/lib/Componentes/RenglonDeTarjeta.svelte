<script>
	import Tarjeta from "./Tarjeta.svelte";
	let {renglonDeCadenas, primBot=$bindable() }= $props();  // define renglonDeCadenas como un atributo
	console.log(renglonDeCadenas);

	let card= new Array(renglonDeCadenas.length); // Variable para almacenar la referencia al componente Tarjeta
	let asociaTarjeta = (ind) =>{
		primBot = card[ind]; // Asigna la tarjeta actual como primer botón
	}

</script>

<!-- Aquí se itera sobre cada cadena en el arreglo renglonDeCadenas -->
{#each renglonDeCadenas as cadena, i	}
	<!-- y se crea una Tarjeta para cada una -->
	<Tarjeta bind:this={card[i]}  propCadena = {cadena} ind={i}
			bind:primerBoton={primBot} {asociaTarjeta}
		/>
{/each}


<!-- 
<Tarjeta propCadena = {renglonDeCadenas[0]}/>
<Tarjeta propCadena = {renglonDeCadenas[1]}/>
<Tarjeta propCadena = {renglonDeCadenas[2]}/>
<Tarjeta propCadena = {renglonDeCadenas[3]}/>
<Tarjeta propCadena = {renglonDeCadenas[4]}/> 
-->