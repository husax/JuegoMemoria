<script>
	let contenido = $state("");
	let {propCadena, primerBoton= $bindable()} = $props();
	let esteBoton; // Define esteBoton como un elemento HTMLButtonElement
	console.log(propCadena);
	//console.log(primerBoton.textContent);
	 	function convierteANumero(cad) {
		return cad.length > 2 ? cad[0]*cad.slice(2) : Number.parseInt(cad); // Convierte la cadena a númer0
	}

	function destapar() {
		contenido = contenido === "" ? propCadena: "";
		if (!(primerBoton === null)) { // Verifica si primerBoton ya ha sido asignado
			let numPB = convierteANumero(primerBoton.textContent);
			let numEste = convierteANumero(propCadena);
			if (numPB === numEste) {
				primerBoton.disabled = true; // Deshabilita el primer botón si las cadenas coinciden
				esteBoton.disabled = true; // Deshabilita este botón también
			} else {
				setTimeout(() => {
					primerBoton.textContent = ""; // Limpia el contenido del primer botón después de un breve retraso
					esteBoton.textContent = ""; // Limpia el contenido de este botón también
					primerBoton.disabled = false; // Habilita el primer botón nuevamente
				}, 1000); // Espera 1 segundo antes de limpiar los botones
			} 
		}
		else {
			primerBoton = esteBoton; // Asigna este botón como el primer botón presionad
			esteBoton.disabled = true; // Deshabilita este botón para evitar que se presione nuevamente
		}
	}
</script>

<button bind:this={esteBoton} onclick ={destapar}>
	{contenido}

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