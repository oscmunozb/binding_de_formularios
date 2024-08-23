<!-- Script JS -->
<script>
export default {
  name: 'App',
  data() {
    return {
      // Datos iniciales que representan la información visual y de texto de la tarjeta.
      // Estos valores se pueden modificar mediante el formulario en la interfaz.
      tituloTarjeta: "Visa Classic Crédito",  // Título que aparece en la parte superior de la tarjeta.
      chipSrc: "/chip.png",  // Ruta de la imagen del chip que se muestra en la tarjeta.
      numeroTarjeta: "400 500 600 700",  // Número de la tarjeta en el formato visual adecuado.
      fechaExpiracion: "01/30",  // Fecha de expiración que aparece en la tarjeta.
      propietario: "William Henry Gates III",  // Nombre del propietario que se muestra en la tarjeta.
      tipoTarjetaSrc: "/visa.png"  // Ruta de la imagen del logo de la tarjeta.
    }
  }
}
</script>

<!-- Template HTML -->
<template>
  <div id="app">
    <!-- Formulario para cambiar los datos de la tarjeta -->
    <form>
      <p class="instrucciones">Cambia los datos por los de tu tarjeta</p>

      <!-- Input para cambiar el título de la tarjeta -->
      <div>
        <label>Título de la tarjeta: </label>
        <input v-model="tituloTarjeta" placeholder="Visa Classic Crédito">
      </div>

      <!-- Input para cambiar la imagen del chip de la tarjeta -->
      <div>
        <label>Chip SRC: </label>
        <input v-model="chipSrc" placeholder="/chip.png">
      </div>

      <!-- Input para cambiar el número de la tarjeta -->
      <div>
        <label>Número: </label>
        <input v-model="numeroTarjeta" placeholder="400 500 600 700">
      </div>

      <!-- Input para cambiar la fecha de expiración de la tarjeta -->
      <div>
        <label>Fecha de expiración: </label>
        <input v-model="fechaExpiracion" placeholder="01/30">
      </div>

      <!-- Input para cambiar el nombre del propietario de la tarjeta -->
      <div>
        <label>Propietario: </label>
        <input v-model="propietario" placeholder="William Henry Gates III">
      </div>

      <!-- Input para cambiar la imagen del logo de la tarjeta -->
      <div>
        <label>Tipo de tarjeta SRC: </label>
        <input v-model="tipoTarjetaSrc" placeholder="/visa.png">
      </div>
    </form>

    <!-- Componente visual que muestra la tarjeta con los datos actuales -->
    <div class="carnet">
      <h3>{{ tituloTarjeta }}</h3>
      <img width="40" :src="`/src/assets/img${chipSrc}`" alt="Chip">
      <div>
        <h2>{{ numeroTarjeta }}</h2>
        <span>Fecha Exp: <b>{{ fechaExpiracion }}</b></span>
      </div>
      <footer>
        <span>{{ propietario }}</span>
        <img width="60" :src="`/src/assets/img${tipoTarjetaSrc}`" alt="Logo tarjeta">
      </footer>
    </div>
  </div>
</template>

<!-- Style CSS -->
<style>
/* Reseteo de márgenes para todos los elementos */
* {
  margin: 0;
}

/* Estilo general del cuerpo del documento */
body {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 60vh;
  font-size: 10px;
  font-family: sans-serif;
}

/* Contenedor principal */
#app {
  display: flex;
  gap: 40px;
}

/* Estilo del formulario */
form {
  padding: 18px;
  border-radius: 20px;
  border: ridge 1px;
  box-shadow: 1px 1px 1px 1px gray;
  font-weight: bold;
  display: flex;
  flex-direction: column;
  gap: 15px;
  justify-content: center;
}

/* Estilo para las filas del formulario */
form div {
  display: grid;
  grid-template-columns: 100px 200px;
  align-items: center;
  gap: 5px;
}

/* Alineación del texto de las etiquetas */
form div label {
  text-align: right;
}

/* Estilo del componente visual de la tarjeta */
.carnet {
  width: 400px;
  height: 230px;
  background: #1c1a1e;
  color: white;
  border-radius: 20px;
  padding: 20px;
  box-shadow: 0px 0px 10px 2px black;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

/* Estilo para las instrucciones del formulario */
.instrucciones {
  text-align: center;
}

/* Estilo de los encabezados dentro del componente de tarjeta */
h3 {
  font-size: 20px;
}

h2 {
  font-size: 30px;
  letter-spacing: 10px;
  margin-bottom: 15px;
  text-shadow: 0px 0px 1px gold;
  font-family: Times;
}

/* Estilo del texto en negrita */
b {
  font-size: 16px;
}

/* Estilo del pie de la tarjeta */
footer {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  font-weight: bold;
  font-size: 18px;
  text-transform: uppercase;
  font-style: italic;
}
</style>
