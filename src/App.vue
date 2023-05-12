<script setup>

import {ref} from "vue";
import Home from "./components/Home.vue";
import Footer from "./components/Footer.vue";
import FacebookIcon from "./components/FacebookIcon.vue";
import Carta from "./components/Carta.vue";
import NuestraEsencia from "./components/NuestraEsencia.vue";

const currentPage = ref('home');

const menuIsActive = ref(false);

const changePage = (page) => {
    currentPage.value = page;
    console.log(currentPage.value);
}

const redirectToFacebook = () => {
    const url = "https://www.facebook.com/pizzeriarossetti?mibextid=ZbWKwL";
    window.open(url, "_blank", "noopener,noreferrer");
}

const redirectToGlovo = () => {
    const url = "https://glovoapp.com/es/es/valencia/pizzeria-rossetti-valencia/"
    window.open(url, "_blank", "noopener,noreferrer");
}

</script>

<template>
    <div id="root-content">

        <nav aria-label="main navigation" class="navbar is-fixed-top" role="navigation">
            <div class="navbar-brand">
                <a class="navbar-item"
                   @click="changePage('home')"
                >
                    <img
                        src="http://pizzeriarossettimanises.com/wp-content/uploads/2019/04/Logotiporossetti_Mesa-de-trabajo-1.jpg"
                        width="212"
                        alt="Pizzeria Rossetti Manises"
                    >
                </a>
                <a
                    role="button"
                    class="navbar-burger"
                    aria-label="menu"
                    aria-expanded="false"
                    @click="menuIsActive = !menuIsActive"
                   :class="{'is-active': menuIsActive}"
                >
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                    <span aria-hidden="true"></span>
                </a>
            </div>

            <div class="navbar-menu" :class="{'is-active': menuIsActive}">
                <div class="navbar-start">
                    <a
                        class="navbar-item"
                    >
                              <span class="icon"
                                    @click="redirectToFacebook"
                              >
                                  <FacebookIcon />
                              </span>
                    </a>
                    <a
                        class="navbar-item"
                        @click="changePage('carta')"
                    >
                        Carta
                    </a>
                    <a class="navbar-item"
                       @click="changePage('nuestra-esencia')"
                    >
                        Nuestra esencia
                    </a>
                    <a
                        class="navbar-item"
                        @click="changePage('contacto')"
                    >
                        Contacto
                    </a>
                </div>

                <div class="navbar-end">
                    <div class="navbar-item">
                        <div class="buttons" id="glovo">
                            <a class="button is-primary" @click="redirectToGlovo">
                                <strong>Comprar por Glovo</strong>
                            </a>
                        </div>
                    </div>
                </div>
            </div>
        </nav>
        <div class="content current-page">
            <Home
                v-if="currentPage === 'home'"
            />
            <Carta
                    v-if="currentPage === 'carta'"
            />
            <NuestraEsencia
                    v-if="currentPage === 'nuestra-esencia'"        
            />
            <p
                v-if="currentPage === 'contacto'"
            >
                Contacto
            </p>
        </div>
        <Footer/>
    </div>
</template>

<style>
body {
    background-color: #f2f2f2;
}

#root-content {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    width: min(100vw, 1200px);
    margin: 0 auto;
    position: relative;
    z-index: 1;
}

#root-content:before{
    content: "";
    position: absolute;
    z-index: -1;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-image: url("/src/assets/background.jpg");
    background-size: 40rem;
    opacity: 0.1;
    background-repeat: repeat;
}

.current-page {
    flex-grow: 1;
}

/* small customizations to have the items centered on mobile */
@media all and (max-width: 1024px) {
    .navbar-item {
        text-align: center;
    }

    #glovo {
        justify-content: center;
    }
}
</style>
