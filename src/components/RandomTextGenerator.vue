<script setup>
import { ref, onMounted } from 'vue';

const quotes = ref([
    { text: 'yoora', author: 'lame' },
    { text: 'james', author: 'town' },
    { text: 'feda', author: 'elvis' },
]);

const currentQuote = ref({ text: '', author: '' });

const getRandomQuote = () => {
    const randomIndex = Math.floor(Math.random() * quotes.value.length);
    currentQuote.value = quotes.value[randomIndex];
};

onMounted(getRandomQuote);
</script>

<template>
    <div class="quote-generator">
        <h1>Random Quote Generator</h1>
        <ul class="quote">
            <li>{{ currentQuote.text }}</li>
            <li>{{ currentQuote.author }}</li>
        </ul>
        <button @click="getRandomQuote">GET Random Quote</button>
    </div>
</template>

<style scoped>
.quote-generator {
    text-align: center;
    margin: 20px;
    font-family: Arial, sans-serif;
}

h1 {
    color: #333;
    margin-bottom: 20px;
}

.quote {
    list-style: none;
    padding: 0;
    margin: 20px 0;
}

.quote li:first-child {
    font-size: 1rem;
    margin-bottom: 10px;
}

.quote li:last-child {
    font-size: 1rem;
    color: #555;
}

button {
    background-color: #007BFF;
    color: white;
    border: none;
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s;
}

button:hover {
    background-color: #0056b3;
}
</style>
