<script setup>
import { ref } from "vue";
import PizzaCard from "./PizzaCard.vue";

const isModalActive = ref(false);
const selectedPizza = ref({
    src: "src/assets/margarita.jpg",
    pizzaTitle: "Maatgarita",
    pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
    pizzaPrice: "10,99"
});

const handleClickPizza = (selection) => {
    if (selection === 'margarita') {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "Maatgarita",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,99"
        };
    } else if (selection === 'napoli') {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "Maatgarita",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,99"
        };
    } else if (selection === 'Sicilia') {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "Maatgarita",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,99"
        };
    } else if (selection === 'gorroma') {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "Maatgarita",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,99"
        };
    } else {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "Maatgarita",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,99"
        };
    }
    isModalActive.value = true;
}

const closeModal = () => {
    isModalActive.value = false;
}

</script>

<template>
    <section class="hero">
        <div class="hero-body">
            <p class="title is-1 has-text-centered">
                PIZZERIA ROSSETTI
            </p>
            <p class="subtitle has-text-centered">
                Tradición italiana
            </p>
        </div>
    </section>
    <img
        id="hero-pizza"
        src="/src/assets/hero-pizza.jpg"
        alt="Pizza"
    />
    <div
        class="container"
    >
        <div class="my-6 px-6">
            <p class="has-text-centered">
                En Pizzeria Rossetti Manises elaboramos de manera artesanal nuestras pizzas y con ingredientes 100% naturales, disponemos de un tamaño unico de pizza de 33cm con el que seguro te quedaras satisfecho, seguimos sumando años de historia ¡ya van 20 años!
            </p>
        </div>
        <div class="my-6 px-6">
            <p class="title is-3 has-text-centered mb-2">
                Nuestra carta
            </p>
            <p class="has-text-centered">Los más vendidos</p>
            <div class="columns mt-6">
                <div class="column is-half">
                    <div class="box pizza-item" @click="handleClickPizza('gorroma')">
                        <p class="mb-0">
                            GORROMA
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                    <div class="box pizza-item" @click="handleClickPizza('Sicilia')">
                        <p class="mb-0">
                            Sicilia
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                </div>
                <div class="column is-half">
                    <div class="box pizza-item" @click="handleClickPizza('napoli')">
                        <p class="mb-0">
                            Napoli
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                    <div class="box pizza-item" @click="handleClickPizza('margarita')">
                        <p class="mb-0">
                            Margarita
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="modal" :class="{ 'is-active': isModalActive }">
        <div class="modal-background" @click="closeModal" ></div>
        <div class="modal-content">
            <PizzaCard
                :src="selectedPizza.src"
                :pizza-ingredients="selectedPizza.pizzaIngredients"
                :pizza-title="selectedPizza.pizzaTitle"
                :pizza-price="selectedPizza.pizzaPrice"
             />
        </div>
        <button class="modal-close is-large" aria-label="close" @click="closeModal"></button>
    </div>
</template>

<style scoped>
#hero-pizza {
    width: 100%;
    height: min(30vh, 400px);
    object-fit: cover;
    object-position: 0 20%;
}

.ingredients {
    font-size: 0.8rem;
}

.pizza-item {
    cursor: pointer;
    transition: transform 0.2s;
}

.pizza-item:hover {
    transform: scale(1.05);
}
</style>