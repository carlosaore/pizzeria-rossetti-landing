<script setup>

import {ref} from "vue";
import Home from "./components/Home.vue";
import Footer from "./components/Footer.vue";
import FacebookIcon from "./components/FacebookIcon.vue";

const currentPage = ref('home');

const changePage = (page) => {
	currentPage.value = page;
	console.log(currentPage.value);
}

const redirectToFacebook = () => {
  const url = "https://www.facebook.com/pizzeriarossetti?mibextid=ZbWKwL";
  window.open(url, "_blank", "noopener,noreferrer");
}

</script>

<template>
    <div id="root-content">
        <div class="main-content">
            <nav aria-label="main navigation" class="navbar" role="navigation">
                <div class="navbar-brand">
                    <a class="navbar-item"
                       @click="changePage('home')"
                    >
                        <img src="http://pizzeriarossettimanises.com/wp-content/uploads/2019/04/Logotiporossetti_Mesa-de-trabajo-1.jpg"
                             width="212"
                            alt="Pizzeria Rossetti Manises"
                        >
                    </a>
                </div>

                <div id="navbarBasicExample" class="navbar-menu">
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
                            <div class="buttons">
                                <a class="button is-primary">
                                    <strong>Comprar por Glovo</strong>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </nav>
        </div>
        <div class="content current-page">
            <Home
                    v-if="currentPage === 'home'"
            />
            <p
                    v-if="currentPage === 'carta'"
            >
                Carta
            </p>
            <p
                    v-if="currentPage === 'nuestra-esencia'"
            >
                Nuestra esencia
            </p>
            <p
                    v-if="currentPage === 'contacto'"
            >
                Contacto
            </p>
        </div>
        <Footer/>
    </div>
</template>

<style scoped>
#root-content {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    width: min(100vw, 1200px);
    margin: 0 auto;
}

.current-page {
    flex-grow: 1;
}

</style>
