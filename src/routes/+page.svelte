<script>
	import RenglonDeTarjetas from "$lib/Componentes/RenglonDeTarjeta.svelte";
	let name = 'world';
	let numeros = ["2x1","2","2x2","4","2x3","6","2x4","8","2x5","10","2x6","12","2x7","14","2x8","16", "2x9","18", "2x10", "20"];
  numeros = numeros.sort(()=>{return Math.random()-0.5});
  console.log(numeros);
	let renglonNum = [numeros.slice(0, 5), numeros.slice(5, 10), numeros.slice(10,15), numeros.slice(15, 20)];
  console.log(renglonNum);
</script>

<!-- Este es un comentario: Aquí van las etiquetas de HTML -->
<h1>Juego de Memoria</h1>
<table>
	<tbody>
		{#each renglonNum as renglon}
		<!-- Aquí se itera sobre cada renglon-->
			<tr>
				<td>
					<RenglonDeTarjetas renglonDeCadenas = {renglon}/>
				</td>
			</tr>
		{/each}


<!-- 
		<tr>
		<td>
			<RenglonDeTarjetas renglonDeCadenas = {renglonNum[0]}/>
		</td>
	</tr>
	<tr>
		<td>
			<RenglonDeTarjetas renglonDeCadenas = {renglonNum[1]}/>
		</td>
	</tr>
	<tr>
		<td>
			<RenglonDeTarjetas renglonDeCadenas = {renglonNum[2]}/>
		</td>
	</tr>
	<tr>
		<td>
			<RenglonDeTarjetas renglonDeCadenas = {renglonNum[3]}/>
		</td>
	</tr>-->
	</tbody>
</table>

<style>
	tr, td {
	height: 110px;
	display:flex;
}
</style>
