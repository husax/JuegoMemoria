<script>
	let contenido = $state("");
	let {propCadena} = $props();
	console.log(propCadena);
	function destapar() {
		contenido = contenido === "" ? propCadena: "";		
	}
</script>

<button id="0" onclick={destapar}>
	{contenido}
</button>


<style>
	button{
  height: 100px;
  width: 100px;
  font-size: 40px;
  color: black;
  font-weight: bold;
}

button:hover{
  cursor: pointer;
}
</style>