<script>
	let contenido = $state("");
	let {propCadena, primerBoton= $bindable(), asociaTarjeta} = $props();
	let esteBoton; // Define esteBoton como un elemento HTMLButtonElement
	console.log(propCadena);
	console.log(primerBoton !== null);
	 	function convierteANumero(cad) {
		return cad.length > 2 ? cad[0]*cad.slice(2) : Number.parseInt(cad); // Convierte la cadena a númer0
	}

	function destapar() {
		contenido = contenido === "" ? propCadena: "";
		console.log(propCadena);
		if (primerBoton !== null) { // Verifica si primerBoton ya ha sido asignado
			console.log(primerBoton.contenido);
			let numPB = convierteANumero(primerBoton.propCadena);
			let numEste = convierteANumero(propCadena);
			if (numPB === numEste) {
				primerBoton.disabled = true; // Deshabilita el primer botón si las cadenas coinciden
				esteBoton.disabled = true; // Deshabilita este botón también
			} else {
				//setTimeout(() => {
					contenido = ""; // Limpia el contenido de este botón también
					primerBoton.contenido="";
					primerBoton.disabled = false; // Habilita el primer botón nuevamente
					esteBoton.disabled = false; // Habilita este botón nuevamente
					primerBoton = null; // Reinicia primerBoton a null para permitir un nuevo par
				//}, 1000); // Espera 1 segundo antes de limpiar los botones
			} 
		}
		else {
			asociaTarjeta(); // Asigna este botón como el primer botón presionad
			esteBoton.disabled = true; // Deshabilita este botón para evitar que se presione nuevamente
		}
	}
</script>

<button bind:this={esteBoton} onclick ={destapar}>
	{contenido === propCadena ? contenido : ""}
</button>


<style>
	button {
  height: 100px;
  width: 100px;
	margin-left: 5px;
	margin-right: 5px;
  font-size: 40px;
  color: black;
  font-weight: bold;
}


button:hover{
  cursor: pointer;
}
</style>