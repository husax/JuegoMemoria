<script>
	import RenglonDeTarjetas from "$lib/Componentes/RenglonDeTarjeta.svelte";
	let primerBoton= $state(null); 
	let numeros = ["2x1","2","2x2","4","2x3","6","2x4","8","2x5","10","2x6","12","2x7","14","2x8","16", "2x9","18", "2x10", "20"];
  numeros = numeros.sort(()=>{return Math.random()-0.5});
  console.log(numeros);
	let renglonNum = [numeros.slice(0, 5), numeros.slice(5, 10), numeros.slice(10,15), numeros.slice(15, 20)];
  console.log(renglonNum);
</script>

<!-- Este es un comentario: Aquí van las etiquetas de HTML -->

<table>
	<thead>
		<tr>
			<th>
				<h1>Juego de Memoria</h1>
			</th>
		</tr>
	</thead>
	<tbody>
			<!-- Aquí se itera sobre cada renglon-->
		{#each renglonNum as renglon}
			<tr>
				<td>
					<RenglonDeTarjetas renglonDeCadenas = {renglon} bind:primBot={primerBoton}/>
				</td>
			</tr>
		{/each}
	</tbody>
</table>

	

<style>
td {
	height: 110px;
	display:flex;
}
</style>
