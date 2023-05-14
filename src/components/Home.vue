<script setup>
import { ref } from "vue";
import PizzaCard from "./PizzaCard.vue";

const isModalActive = ref(false);
const selectedPizza = ref({
    src: "src/assets/quattro-formaggi.jpg",
    pizzaTitle: "QUATTRO FORMAGGI",
    pizzaIngredients: "Ingredientes: Tomate, mozzarella, emental, roquefort y parmesano",
    pizzaPrice: "9,90"
});

const handleClickPizza = (selection) => {
    if (selection === 'quattro-formaggi') {
        selectedPizza.value = {
            src: "src/assets/quattro-formaggi.jpg",
            pizzaTitle: "QUATTRO FORMAGGI",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, emental, roquefort y parmesano",
            pizzaPrice: "8,90"
        };
    } else if (selection === 'cosa-nostra') {
        selectedPizza.value = {
            src: "src/assets/cosa-nostra.jpg",
            pizzaTitle: "COSA NOSTRA",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, pepperoni, bacon y cebolla",
            pizzaPrice: "8,90"
        };
    } else if (selection === 'deliziosa') {
        selectedPizza.value = {
            src: "src/assets/deliziosa.jpg",
            pizzaTitle: "DELIZIOSA",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "10,50"
        };
    } else if (selection === 'margarita') {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "MARGARITA",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante",
            pizzaPrice: "6,50"
        };
    } else {
        selectedPizza.value = {
            src: "src/assets/margarita.jpg",
            pizzaTitle: "MARGARITA",
            pizzaIngredients: "Ingredientes: Tomate, mozzarella, oregano",
            pizzaPrice: "6,50€"
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
            <p class="title is-4 has-text-centered mb-2">
                Nuestra carta
            </p>
            <p class="has-text-centered">Los más vendidos</p>
            <div class="columns mt-6">
                <div class="column is-half">
                    <div class="box pizza-item" @click="handleClickPizza('quattro-formaggi')">
                        <p class="mb-0">
                            QUATTRO FORMAGGI
                        </p>
                        <p class="mb-0">8,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, emental, roquefort y parmesano
                        </p>
                    </div>
                    <div class="box pizza-item" @click="handleClickPizza('cosa-nostra')">
                        <p class="mb-0">
                            COSA NOSTRA
                        </p>
                        <p class="mb-0">8,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, pepperoni, bacon y cebolla

                        </p>
                    </div>
                </div>
                <div class="column is-half">
                    <div class="box pizza-item" @click="handleClickPizza('deliziosa')">
                        <p class="mb-0">
                            DELIZIOSA
                        </p>
                        <p class="mb-0">10,50€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, roquefort, carne y parmesano
                        </p>
                    </div>
                    <div class="box pizza-item" @click="handleClickPizza('margarita')">
                        <p class="mb-0">
                            MARGARITA
                        </p>
                        <p class="mb-0">6,50€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, oregano
                        </p>

                    </div>

                </div>

            </div>
            <button class="button" @click="handleClickButton('margarita')">Consulta nuestra carta</button>
        </div>

    </div>

    <div class="modal" :class="{ 'is-active': isModalActive }">
        <div class="modal-background" @click="closeModal" ></div>
        <div class="modal-content p-6">
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
    height: min(35vh, 400px);
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

.modal-content {
    overflow-y: hidden;
}
</style>