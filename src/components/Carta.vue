<script setup></script>

<template>
  <div class="content p-6">
    <h1 class="has-text-centered">Nuestra carta</h1>
    <p class="p--intro">
      Nuestras pizzas son elaboradas con ingredientes frescos, tradición italiana y 20 años de experiencia preparando
      pizzas.
    </p>
    <p class="has-text-centered">Esperamos que las disfrutes.</p>
    <h2 class="has-text-centered">Nuestras Pizzas</h2>
    <table id="pizza-menu-table">
      <tbody >
        <tr>
          <td>Americana</td>
          <td>8,50€</td>
          <td>Tomate, mozzarella, bacon y huevo</td>
        </tr>
        <tr>
          <td>Capricciosa</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, alcachofas, york, champiñones y olivas</td>
        </tr>
        <tr>
          <td>Corleone</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, chorizo, salami, pimiento, huevo y picante</td>
        </tr>
        <tr>
          <td>Cosa Nostra</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, pepperoni, bacon y cebolla</td>
        </tr>
        <tr>
          <td>Deliziosa</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, roquefort, emental, carne, cebolla, huevo y parmesano</td>
        </tr>
        <tr>
          <td>Margarita</td>
          <td>6,50€</td>
          <td>Tomate, mozzarella, oregano</td>
        </tr>
        <tr>
          <td>Pompei</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, york, salami, champiñones y olivas</td>
        </tr>
        <tr>
          <td>Quattro stagioni</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, atun, alcachofas, york y champiñones</td>
        </tr>
        <tr>
          <td>Tentazione</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, york, berenjenas, salami y champiñones</td>
        </tr>
        <tr>
          <td>Tricolore</td>
          <td>8,90€</td>
          <td>Tomate, mozzarella, carne picada y pimiento</td>
        </tr>
        <tr>
          <td>Vegetariana</td>
          <td>9,50€</td>
          <td>Tomate, mozzarella, berenjena, cebolla, alcachofa, pimiento y olivas</td>
        </tr>
      </tbody>
    </table>
    <h2 class="has-text-centered">Bebidas</h2>
    <table id="beverages-menu-table">
      <tbody>
        <tr>
          <td>Coca-Cola, Fanta limón o Naranja (lata)</td>
          <td>1,50€</td>
        </tr>
        <tr>
          <td>Botella 2L de Coca-Cola</td>
          <td>2,90€</td>
        </tr>
        <tr>
          <td>Cerveza (lata)</td>
          <td>1,50€</td>
        </tr>
        <tr>
          <td>Cerveza (1 Litro)</td>
          <td>2,50€</td>
        </tr>
        <tr>
          <td>Lambrusco tinto o rosado (75cl)</td>
          <td>8,50€</td>
        </tr>
        <tr>
          <td>Agua 1,5 litros</td>
          <td>1,50€</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
#pizza-menu-table {
    width: max-content;
    margin: 0 auto;
}

#pizza-menu-table td {
    text-align: left;
}

#pizza-menu-table tr td:nth-child(1) {
    font-weight: bold;
}

#beverages-menu-table td {
    text-align: left;
}

#beverages-menu-table tr td:nth-child(1) {
    font-weight: bold;
}

.p--intro {
    text-align: center;
    font-style: italic;
    font-size: 1.2rem;
    color: green;
    text-transform: uppercase;
    text-shadow: 1px 1px 1px #ccc;
}
</style>
