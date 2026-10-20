<script setup>
import { ref } from 'vue'

const name = ref('Alex Morgan')
const bio = ref('I am learning to build interactive web pages.')
// TASK 4: Create a reactive likes counter.
// TASK 5: Create reactive showFact and fact values.
</script>

<template>
  <main>
    <article class="card">
      <p class="eyebrow">MY FIRST VUE PAGE</p>
      <h1>{{ name }}</h1>
      <p>{{ bio }}</p>
      <!-- TASK 2: Add a labelled input with v-model="name" here. -->
      <!-- TASK 4: Add a button, click counter and @click here. -->
      <!-- TASK 5: Add a toggle button and v-if paragraph here. -->
    </article>
  </main>
</template>

<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #eef2f6;
  color: #192d3a;
}
main { min-height: 100vh; display: grid; place-items: center; padding: 24px; }
.card { width: 100%; max-width: 520px; padding: 32px; background: white; border-radius: 18px; }
.eyebrow { color: #24634a; font-size: 12px; font-weight: bold; letter-spacing: 2px; }
h1 { overflow-wrap: anywhere; }
label { display: block; margin-top: 24px; font-weight: bold; }
input { width: 100%; padding: 12px; margin-top: 8px; border: 1px solid #637580; border-radius: 8px; font: inherit; }
button { padding: 12px 16px; margin: 16px 8px 0 0; border: 0; border-radius: 8px; background: #24634a; color: white; font: inherit; cursor: pointer; }
button:hover { background: #174630; }
:focus-visible { outline: 3px solid #b55000; outline-offset: 3px; }
/* TASK 3: Personalise the background, card, heading and buttons. */
</style>
