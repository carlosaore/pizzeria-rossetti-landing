<script setup></script>

<template>
  <div class="content p-6">
    <h1>Nuestra historia</h1>
    <p>
      Nuestra historia comienza hace más de 20 años, cuando Giovanni, un chef apasionado que creció en Nápoles, decidió
      cumplir su sueño de toda la vida de abrir su propia pizzería. Rosseti se estableció en el corazón de la ciudad de
      Valencia, con la misión de llevar la auténtica pizza de estilo napolitano a nuestra comunidad. Giovanni se
      abastece de los ingredientes más frescos y utiliza técnicas tradicionales, para crear pizzas crujientes y llenas
      de sabor.
    </p>
    <h2>Nuestra esencia</h2>
    <div id="header-title-wrapper-1" class="header-title-wrapper">
      <h3>Contamos con 20 años de historia y con tu preferencia seguiremos sumando.</h3>
    </div>
    <div id="header-title-wrapper-2" class="header-title-wrapper">
      <h3>Elaboramos nuestras pizzas con ingredientes 100% naturales.</h3>
    </div>
    <div id="header-title-wrapper-3" class="header-title-wrapper">
      <h3>Disponemos de un tamaño único de pizza de 33 centímetros, con el que seguro queradarás satisfecho.</h3>
    </div>
  </div>
</template>
<style>
.header-title-wrapper {
  width: 100%;
  height: 30vh;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  padding: 0 2rem;
  position: relative;
}

#header-title-wrapper-1 {
  background-image: url("/src/assets/nuestra-esencia-1.png");
}

#header-title-wrapper-2 {
  background-image: url("/src/assets/nuestra-esencia-2.png");
}

#header-title-wrapper-3 {
  background-image: url("/src/assets/nuestra-esencia-3.png");
}

/* add an overlay to the image */
.header-title-wrapper:before {
  content: "";
  position: absolute;
  z-index: 2;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: black;
  opacity: 0.4;
}

.header-title-wrapper h3 {
  width: 90%;
  color: white;
  z-index: 3;
}
</style>
