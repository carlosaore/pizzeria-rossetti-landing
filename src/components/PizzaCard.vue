<script setup>
const props = defineProps({
    src: String, 
    pizzaTitle: String,
    pizzaPrice: String,
    pizzaIngredients: String
})

</script>

<template>
   <div class="card">
  <div class="card-image">
    <figure class="image is-4by3">
      <img :src="props.src" alt="Placeholder image">
    </figure>
  </div>
  <div class="card-content">
    <div class="media">      
      <div class="media-content">
        <p class="title is-4">{{pizzaTitle}}</p>
        <p class="subtitle is-6">{{pizzaPrice}}$</p>
      </div>
    </div>

    <div class="content">
      {{pizzaIngredients}}
    </div>
  </div>
</div>

</template>

<style>
</style>