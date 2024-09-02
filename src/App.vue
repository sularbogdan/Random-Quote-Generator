<script setup>
import {ref, onMounted} from 'vue'

const quotes = ref([
  {
    text: "The only way to do great work is to love what you do.",
    author: "Steve Jobs",
  },
  {
    text: "Believe you can and you're halfway there.",
    author: "Theodore Roosevelt",
  },
  {
    text: "Life is what happens when you're busy making other plans.",
    author: "John Lennon",
  },
])

const currentQuote = ref({text: ' ', author: ' '})

const getRandomQuotes = () => {
  const randomIndex = Math.floor(Math.floor(Math.random() * quotes.value.length))
  currentQuote.value = quotes.value[randomIndex]

}

onMounted(getRandomQuotes)

</script>

<template>
  <div class = " quote-generator">
    <h1 class = "app-title">Random Quote Generator</h1>
    <blockquote class="quote-container">
      <p>{{ currentQuote.text }}</p>
      <cite>{{ currentQuote.author}}</cite>
    </blockquote>

    <button @click="getRandomQuotes" class="quote-button">Random Quote</button>
  </div>
</template>

<style scoped>

.quote-generator {
  max-width: 400px;
  text-align: center;
  margin: 100px auto;
  padding: 20px;
  border: 5px solid blue;
  border-radius: 8px;
  box-shadow: 0 2px 4px black;

}

.app-title {
  font-size: 30px;
  font-family:Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
  color: grey;
}

.quote-container {
  background-color: whitesmoke;
  padding: 20px;
  border: 1px solid black;
  margin-bottom: 30px;
}
p {
  font-size: 18px;
  margin-bottom: 10px;
}

cite {
  font-style: normal;
  color: #777;
}

.quote-button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #3498db;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.quote-button:hover {
  background-color: #2980b9;
}



</style>