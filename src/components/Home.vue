<script setup>
import { ref } from "vue";

const isModalActive = ref(false);
const selectedPizzaHref = ref("src/assets/margarita.jpg");

const handleClickPizza = (selectedPizza) => {
    if (selectedPizza === 'margarita') {
        selectedPizzaHref.value = "src/assets/margarita.jpg";
    } else if (selectedPizza === 'napoli') {
        selectedPizzaHref.value = "src/assets/hero-pizza.jpg";
    } else if (selectedPizza === 'Sicilia') {
        selectedPizzaHref.value = "src/assets/hero-pizza.jpg";
    } else if (selectedPizza === 'gorroma') {
        selectedPizzaHref.value = "src/assets/hero-pizza.jpg";
    } else {
        selectedPizzaHref.value = "src/assets/margarita.jpg";
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
        src="src/assets/hero-pizza.jpg"
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
                    <div class="box pizza-item"
                         @click="handleClickPizza('gorroma')"
                    >
                        <p class="mb-0">
                            GORROMA
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                    <div class="box pizza-item"
                         @click="handleClickPizza('Sicilia')"
                    >
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
                    <div class="box pizza-item"
                         @click="handleClickPizza('napoli')"
                    >
                        <p class="mb-0">
                            Napoli
                        </p>
                        <p class="mb-0">10,90€</p>
                        <p class="ingredients">
                            Ingredientes: Tomate, mozzarella, salami a la pimienta, scamorza, provolone y salsa picante
                        </p>
                    </div>
                    <div class="box pizza-item"
                         @click="handleClickPizza('margarita')"
                    >
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
    <div class="modal"
         :class="{ 'is-active': isModalActive }"
    >
        <div class="modal-background"
             @click="closeModal"
        ></div>
        <div class="modal-content">
            <p class="image is-4by3">
                <img
                    :src="selectedPizzaHref"
                    alt="">
            </p>
        </div>
        <button class="modal-close is-large" aria-label="close"
                @click="closeModal"
        ></button>
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