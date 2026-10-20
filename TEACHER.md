# Teacher notes — IntelliJ Vue lab

**Assumption:** students have already been shown how to create and run a Vue 3 project in IntelliJ. This lab continues that workflow using JavaScript and `<script setup>`. Allow 45–60 minutes; omit Task 5 for a shorter session.

Distribute `starter/App.vue` and `README.md`. Keep `solution/App.vue` as your reference. Each component replaces `src/App.vue` in a generated Vue project; this pack intentionally does not include another project scaffold.

Before class, check the starter in the same project template used by students. Remove generated global CSS imports from main.js/main.ts so the demo layout does not override the lab. Keep the App import and mount code. No additional components or routing are needed.

Demonstrate the three App.vue sections, change a ref's initial value, then connect the input using v-model. Explain that template expressions unwrap refs, while JavaScript functions use `.value` (for example `likes.value = 0`). The inline template handlers in this lab do not need `.value`.

Assessment: one point each for personalised data, live name binding, a working counter, a working fact toggle, and four intentional CSS changes (5 total).

Expected reflection: changing name updates the interpolated heading and bound input; @click handles an event, while v-if conditionally renders content.

Acceptance checks in your IntelliJ project: starter shows the initial card; solution name edits update the heading, three likes show 3, the fact starts hidden and toggles twice. Reload resets the state. Check keyboard access and narrow-screen layout. The solution retains the base style; students should make their own CSS choices.
