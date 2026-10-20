<script setup>
import { ref } from 'vue'

const name = ref('Levente Alfoldy')
const bio = ref('Hit me, Batman!')
const likes = ref(0)
const showFact = ref(false)
const fact = ref('Nicholas Cage was not ACTUALLY set on fire while filming the movie Ghost Rider.')
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
      <label for="name">Your name</label>
      <input id="name" v-model="name" maxlength="60">
      <!-- TASK 4: Add a button, click counter and @click here. -->
      <button type="button" @click="likes++">Like this page</button>
      <p aria-live="polite">Likes: {{ likes }}</p>
      <!-- TASK 5: Add a toggle button and v-if paragraph here. -->
      <button type="button" @click="showFact = !showFact"
              :aria-expanded="showFact" aria-controls="fact">
        {{ showFact ? 'Hide fun fact' : 'Show fun fact' }}
      </button>
      <p id="fact" v-if="showFact">{{ fact }}</p>
    </article>
  </main>
</template>

<style>
* { box-sizing: border-box; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #db00ff;
  color: #192d3a;
}
main { min-height: 100vh; display: grid; place-items: center; padding: 24px; }
.card { width: 100%; max-width: 520px; padding: 16px; background: white; border-radius: 6px; }
.eyebrow { color: #24634a; font-size: 12px; font-weight: bold; letter-spacing: 2px; }
h1 { overflow-wrap: anywhere; font-size: 32px; font-weight: 200; }
label { display: block; margin-top: 24px; font-weight: bold; }
input { width: 100%; padding: 12px; margin-top: 8px; border: 1px solid #637580; border-radius: 8px; font: inherit; }
button { padding: 12px 16px; margin: 16px 8px 0 0; border: 0; border-radius: 8px; background: #04ff00; color: white; font: inherit; cursor: pointer; }
button:hover { background: #174630; }
:focus-visible { outline: 3px solid #b55000; outline-offset: 3px; }
/* TASK 3: Personalise the background, card, heading and buttons. */
</style>
