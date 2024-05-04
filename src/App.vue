<script setup>
import { loadSlim } from "tsparticles-slim";

const particlesInit = async (engine) => {
    await loadSlim(engine);
};

const particlesLoaded = async (container) => {
    console.log("Particles container loaded", container);
};

// Versões do tsparticles que eu utilizei:

/* 
    package.json
    "tsparticles": "^2.2.4",
    "vue3-particles": "^2.2.4",
*/

// Snow options
const options = {
    background: {
        color: "#000000",
        // Em um contexto de um website que precisa necessariamente de um backgroumd, remover isso para ficar só a neve, sem o fundo atrapalhando.
    },
    particles: {
        color: {
            value: ["#FFFFFF", "#FFd700"],
        },
        move: {
            direction: "bottom",
            enable: true,
            outModes: {
                default: "out",
            },
            size: true,
            speed: {
                min: 1,
                max: 2,
            },
        },
        number: {
            density: {
                enable: true,
                area: 1200,
            },
            value: 100,
        },
        opacity: {
            value: 0.6,
        },
        shape: {
            type: "image",
            options: {
                image: [
                    {
                        src: "/public/images/snow.png",
                        width: 15,
                        height: 15,
                        particles: {
                            size: {
                                value: 8,
                            },
                        },
                    },
                ],
            },
        },
        size: {
            value: {
                min: 1,
                max: 2,
            },
        },
        roll: {
            darken: {
                enable: true,
                value: 30,
            },
            enlighten: {
                enable: true,
                value: 30,
            },
            enable: true,
            speed: {
                min: 15,
                max: 25,
            },
        },
        wobble: {
            enable: true,
            distance: 15,
            speed: 10,
        },
    },
};


const hohoho = new Date().getMonth() == 11; // mês que você quer que a função seja ativa

/* 
0 - Janeiro
1 - Fevereiro
2 - Março
3 - Abril
4 - Maio
5 - Junho
6 - Julho
7 - Agosto
8 - Setembro
9 - Outubro
10 - Novembro
11 - Dezembro
etc...
*/
</script>

<template>
    <div id="app">
        <vue-particles
            v-if="hohoho"
            id="tsparticles"
            :particlesInit="particlesInit"
            :particlesLoaded="particlesLoaded"
            :options="options"
        />
    </div>
</template>

<style scoped></style>
