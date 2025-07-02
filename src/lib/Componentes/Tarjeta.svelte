<script>
	let contenido = $state("");
	let bloquea = $state(false);
	let {propCadena, ind, primerBoton= $bindable(), asociaTarjeta} = $props();
	let esteBoton; // Define esteBoton como un elemento HTMLButtonElement
	console.log(propCadena);
	console.log(primerBoton !== null);
	function convierteANumero(cad) {
		return cad.length > 2 ? cad[0]*cad.slice(2) : Number.parseInt(cad); // Convierte la cadena a númer0
	}

	export function setContenido (){
		contenido = contenido === "" ? propCadena: "";
	}

	export function getContenido  (){
		return contenido;
	}
	export function getPropCadena () {
		return propCadena;
	}

	export function toogle() {
		bloquea = !bloquea; // Cambia el estado de bloquea
	}

	function destapar() {
		setContenido(); // Cambia el contenido del botón al valor de propCaden
		console.log(propCadena);
		if (primerBoton !== null) { // Verifica si primerBoton ya ha sido asignado
			let numPB = convierteANumero(primerBoton.getPropCadena());
			let numEste = convierteANumero(propCadena);
			if (numPB === numEste) {
				toogle(); // Deshabilita este botón
				primerBoton= null;
			} else {
				setTimeout(() => {
					contenido = ""; // Limpia el contenido de este botón
					primerBoton.setContenido(); // Limpia el contenido del primer botón
					primerBoton.toogle(); // Habilita el primer botón nuevamente
					esteBoton.disabled = false; // Habilita este botón nuevamente
					primerBoton = null; // Reinicia primerBoton a null para permitir un nuevo par
				}, 1000); // Espera 1.5 segundos antes de limpiar los botones
			} 
		}
		else {
			asociaTarjeta(ind); // Asigna este botón como el primer botón presionado
			toogle(); // Deshabilita este botón para evitar que se presione nuevamente
		}
	}
</script>

<button bind:this={esteBoton} disabled={bloquea}  onclick={destapar}>
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