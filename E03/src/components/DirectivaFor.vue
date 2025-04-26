<script setup lang="ts">
import { ref, type Ref } from 'vue';

interface Pelicula {
    nombre: string;
    año_estreno: number;
    genero: string;
    pais_origen: string;
    clasificacion: string;
}

let countries: Ref<Array<string>> = ref([
    "Argentina",
    "Brasil",
    "Canadá",
    "Chile",
    "Colombia",
    "Costa Rica",
    "Ecuador",
    "España",
    "Estados Unidos",
    "Francia",
    "Alemania",
    "Guatemala",
    "Honduras",
    "Italia",
    "México",
    "Nicaragua",
    "Panamá",
    "Paraguay",
    "Perú",
    "Uruguay"
])

let peliculas: Ref<Array<Pelicula>> = ref([
    {
        "nombre": "Tenet",
        "año_estreno": 2020,
        "genero": "Ciencia ficción",
        "pais_origen": "Estados Unidos",
        "clasificacion": "PG-13"
    },
    {
        "nombre": "Duna",
        "año_estreno": 2021,
        "genero": "Ciencia ficción",
        "pais_origen": "Estados Unidos",
        "clasificacion": "PG-13"
    },
    {
        "nombre": "Nomadland",
        "año_estreno": 2020,
        "genero": "Drama",
        "pais_origen": "Estados Unidos",
        "clasificacion": "R"
    },
    {
        "nombre": "La mano de Dios",
        "año_estreno": 2021,
        "genero": "Drama",
        "pais_origen": "Italia",
        "clasificacion": "R"
    },
    {
        "nombre": "Drive My Car",
        "año_estreno": 2021,
        "genero": "Drama",
        "pais_origen": "Japón",
        "clasificacion": "NR"
    },
    {
        "nombre": "Top Gun: Maverick",
        "año_estreno": 2022,
        "genero": "Acción",
        "pais_origen": "Estados Unidos",
        "clasificacion": "PG-13"
    },
    {
        "nombre": "RRR",
        "año_estreno": 2022,
        "genero": "Acción",
        "pais_origen": "India",
        "clasificacion": "NR"
    },
    {
        "nombre": "Barbie",
        "año_estreno": 2023,
        "genero": "Comedia",
        "pais_origen": "Estados Unidos",
        "clasificacion": "PG-13"
    },
    {
        "nombre": "Oppenheimer",
        "año_estreno": 2023,
        "genero": "Biografía",
        "pais_origen": "Estados Unidos",
        "clasificacion": "R"
    },
    {
        "nombre": "El agente nocturno",
        "año_estreno": 2023,
        "genero": "Thriller",
        "pais_origen": "Canadá",
        "clasificacion": "TV-MA"
    }
])

type Genero = "Ciencia ficción" | "Drama" | "Acción" | "Comedia" | "Biografía" | "Thriller";

const generoEmoji: Record<Genero, string> = {
    "Ciencia ficción": "🚀",
    "Drama": "🎭",
    "Acción": "💥",
    "Comedia": "😂",
    "Biografía": "📖",
    "Thriller": "🕵️"
};

function getEmoji(genero: string): string {
    return generoEmoji[genero as Genero] ?? "❓"
}
</script>

<template>
    <p>Paises</p>
    <ul>
        <li v-for="(country, index) in countries" :key="index">{{ index + 1 }} - {{ country }}</li>
    </ul>

    <p>Peliculas</p>
    <ul class="list-movies">
        <li v-for="(pelicula, index) in peliculas" :key="index">
            <p class="name">{{ pelicula.nombre }}</p>
            <p class="gender">{{ `${pelicula.genero} - ${getEmoji(pelicula.genero)}` }}</p>
            <p class="country">{{ pelicula.pais_origen }}</p>
            <p class="year">{{ pelicula.año_estreno }}</p>
            <p class="classification">{{ pelicula.clasificacion }}</p>
        </li>
    </ul>
</template>

<style scoped>
.list-movies {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
    color: #555;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;

    & li {
        border: 1px solid #ccc;
        border-radius: 4px;
        padding: 10px;
        width: 180px;
        height: 160px;
        margin-bottom: 10px;
    }

    & p {
        line-height: 12px;
    }

    & .name {
        text-align: center;
        font-weight: bold;
        text-transform: uppercase;
    }

    & .gender {
        font-size: 12px;
        text-align: center;
    }
}
</style>
