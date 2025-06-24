<script>
	import Tarjeta from "./Tarjeta.svelte";
	let {renglonDeCadenas }= $props();  // define renglonDeCadenas como un atributo
	console.log(renglonDeCadenas);
</script>

<Tarjeta propCadena = {renglonDeCadenas[0]}/>
<Tarjeta propCadena = {renglonDeCadenas[1]}/>
<Tarjeta propCadena = {renglonDeCadenas[2]}/>
<Tarjeta propCadena = {renglonDeCadenas[3]}/>
<Tarjeta propCadena = {renglonDeCadenas[4]}/>