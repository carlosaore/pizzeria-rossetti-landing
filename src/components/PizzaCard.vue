<script setup>
const props = defineProps({
  src: String,
  pizzaTitle: String,
  pizzaPrice: String,
  pizzaIngredients: String,
});
</script>

<template>
  <div class="card">
    <div class="card-image">
      <img :src="props.src" alt="Placeholder image" class="image" />
    </div>
    <div class="card-content">
      <div class="content">
        <p class="title is-4">{{ pizzaTitle }}</p>
        <p class="subtitle is-6">{{ pizzaPrice }}$</p>
        {{ pizzaIngredients }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.image {
  height: auto;
  max-height: 50vh;
  width: 100%;
  object-fit: cover;
}
</style>
