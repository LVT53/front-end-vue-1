# Vue starter lab: My interactive profile

**Time:** 45–60 minutes | **Level:** beginner  
**Prerequisites:** basic HTML tags, CSS selectors and JavaScript variables.

Build one page introducing yourself. Give it your own style, a live name editor,
a like counter and a button that reveals a fun fact.

## Start here — IntelliJ
1. Create or open a **Vue 3 project in IntelliJ**, using the process demonstrated in class. Use JavaScript and the standard Vue/Vite template; no router is needed.
2. Install project dependencies if you have not already done so (`npm install` in IntelliJ's terminal, from the folder containing `package.json`).
3. Replace the contents of `src/App.vue` with `starter/App.vue` from this pack. Make a backup first if your project already contains work.
4. In `src/main.js` (or `src/main.ts`), remove any imports of generated demo styles such as `./assets/main.css` or `./style.css`. Keep the Vue import, App import and app mounting code. The lab's styles are all in App.vue.
5. Start the project using the run configuration shown in class. For a Vite project you can also run `npm run dev` in IntelliJ's terminal.
6. Open the local URL printed by the development server. You should see a profile card. Keep the server running; save your edits to see updates in the browser.

These are **replacement component files**, not a standalone project. Use them inside your generated project. Do not open App.vue directly in a browser.

## Learning goals
- Explain the roles of HTML, CSS and JavaScript.
- Display reactive data using `{{ }}`.
- Connect an input with `v-model`.
- Respond to clicks with `@click` and show content with `v-if`.

## One file, three sections
All the work is in `src/App.vue`:

| Section | Purpose |
| --- | --- |
| `<script setup>` | JavaScript: imports and reactive data |
| `<template>` | HTML page structure and Vue bindings |
| `<style>` | CSS colours, spacing, typography and layout |

`ref()` creates reactive state. In the template, Vue unwraps refs automatically,
so write `{{ name }}`. In JavaScript functions, read or change a ref using `.value`.

## Task 1 — Make it yours (5 minutes)
In the `<script setup>` section of `src/App.vue`, change the text inside the `name` and `bio` refs. Save.
Find `{{ name }}` and `{{ bio }}` in the template: Vue replaces these expressions
with the matching data values. Keep your text inside quotes.

**Checkpoint:** the card displays your name and a short introduction.

## Task 2 — Edit the name live (10 minutes)
Replace the TASK 2 comment in the `<template>` section with:

```html
<label for="name">Your name</label>
<input id="name" v-model="name" maxlength="60">
```

`v-model` keeps the input and the `name` property in sync.

**Checkpoint:** type into the input. The heading changes immediately, without
refreshing. A refresh restores the original data; this lab does not save changes.

## Task 3 — Style your page (10 minutes)
In the `<style>` section, change at least four things:
- The page background colour.
- The card's padding or border radius.
- The heading's size or colour.
- The button background colour (visible after Task 4).

Keep text readable and preserve the visible keyboard focus outline.
Try a narrow browser window: the card should still fit.

**Checkpoint:** the page has a clear personal style and no horizontal scrolling.

## Task 4 — Add a like counter (10 minutes)
Add this line in `<script setup>`, below the existing refs:

```js
const likes = ref(0)
```

Replace the TASK 4 comment in the `<template>` section with:

```html
<button type="button" @click="likes++">Like this page</button>
<p aria-live="polite">Likes: {{ likes }}</p>
```

`@click` runs the JavaScript expression when the button is clicked.
`likes++` increases `likes` by one. Vue updates the displayed number.

**Checkpoint:** three clicks show `Likes: 3`.

## Task 5 — Reveal a fun fact (10 minutes)
Add these lines in `<script setup>`:

```js
const showFact = ref(false)
const fact = ref('I can name five constellations.')
```

Replace the TASK 5 comment in the `<template>` section with:

```html
<button type="button" @click="showFact = !showFact"
        :aria-expanded="showFact" aria-controls="fact">
  {{ showFact ? 'Hide fun fact' : 'Show fun fact' }}
</button>
<p id="fact" v-if="showFact">{{ fact }}</p>
```

`!` flips a Boolean between true and false. `v-if` includes the paragraph only
when `showFact` is true. The `:` binds an attribute to a JavaScript value.
The conditional expression chooses the button label.

**Checkpoint:** the button shows and hides the fact and changes its label.

## Finish and submit (5 minutes)
Submit your `src/App.vue` file, plus a screenshot of your finished page.
Check that:
- Your own name and bio appear.
- The input changes the heading immediately.
- The counter increases on each click.
- The fact starts hidden and can be shown and hidden again.
- At least four CSS changes are visible.
- You can reach the input and buttons using Tab and activate buttons with Enter.

Answer briefly: What does Vue update when `name` changes? What is the difference
between `@click` and `v-if`?

## Optional challenges
- Add a reset button using `@click="likes = 0"`.
- Add a labelled text input to edit the bio with `v-model`.
- Add a hobbies array and render it with `v-for` (look up stable `:key` values).

## Troubleshooting
- **Blank page:** check IntelliJ's terminal and the browser Developer Tools Console. Confirm the development server is running.
- **Syntax error:** check matching quotes, brackets and closing tags.
- **Literal {{ name }} appears:** confirm you opened the development-server URL, and that main.js still mounts App.
- **Button does nothing:** check property spelling and keep it inside `<template>`.
- **Changes do not appear:** save App.vue and confirm you are viewing the URL printed by your running project.

## Reference
Vue's official quick start: https://vuejs.org/guide/quick-start.html

Vue single-file components: https://vuejs.org/guide/scaling-up/sfc.html
