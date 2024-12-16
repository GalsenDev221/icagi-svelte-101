---
layout: cover
title: Introduction à Svelte
drawings:
  persist: false
---

# Introduction à Svelte

Presenté par **Papa Elhadj Abdoulaye NDOYE**

<div class="abs-br m-6 flex gap-2">
  <a href="https://galsen.dev" target="_blank" alt="Galsen DEV website"  class="slidev-icon-btn opacity-50 !border-none !hover:opacity-100 !hover:bg-transparent">
    <galsen-icon />
  </a>
</div>

---

# Plan

<v-clicks>

- 🤔 C'est quoi Svelte ?
- ✨ Le système de réactivité
- 🪄 Runes
- 🧑🏽‍💻 Coding time
- 📋 Svelte + Todo

</v-clicks>

<!-- TODO: make this a component -->
<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

<!--
We need to
- present the framework to the audience
- explain the concept of reactivity
- show the syntax - when considering Svelte as a language
- present what we'll build
    - list the pre-requisites
    - make sure they are familiar with JS basics
-->
---

<div class="h-full flex items-center justify-between">
    <my-avatar />
    <div>
        <h2>Papa Elhadj Abdoulaye NDOYE</h2>
        <ul>
            <li>💻 Développeur Fullstack</li>
            <li>🤵 Chargé des programmes et activités de Galsen DEV</li>
            <li class="animate-pulse">🕹️ #1 Tetris au Senegal</li>
        </ul>
    </div>
</div>

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

---

# 🤔 C'est quoi Svelte ?

Framework JavaScript moderne pour construire des interfaces utilisateur web.

<v-clicks>

- Crée en novembre 2006 par <span class="text-orange-600">Rich Harris</span>
- Actuellemnt à la <span class="text-orange-600">version 5</span>
- Fonctionne comme un *compileur* afin créer des interfaces web <span class="text-orange-600">réactives</span>
- Aucun script ou bibliothèque supplémentaire n'est expédié en <span class="text-orange-600">production</span>

</v-clicks>

<div class="m-[3.5rem] abs-br">
    <svelte-icon class="h-40 w-40" />
</div>

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

<!-- Svelte est un framework pour construire des interfaces utilisateur sur le web. Il utilise un compilateur pour transformer des composants déclaratifs écrits en HTML, CSS et JavaScript... -->

---

# ✨ Le système de réactivité

Le cœur de Svelte réside dans son système de réactivité.


````md magic-move
```html {*|4,1,3,13|3,13,5,12|3,13,7-10|3,13,9,1|*}
<button id="counter">Compteur: 0</button>

<script>
  let count = 0;
  const counterEl = document.getElementById('counter');

  function increment() {
    count += 1;
    counterEl.textContent = `Compteur: ${count}`;
  }

  counterEl.addEventListener('click', increment);
</script>
```

```svelte {*|1,3,9,4|3,9,6-8|*}
<button onclick={increment}>Compteur: {count}</button>

<script>
let count = $state(0);

function increment() {
    count += 1;
}
</script>
```
````

<script setup>
    import { ref } from 'vue'
    const counter = ref(0)
</script>

<div class="mt-12 flex items-center justify-center">
    <button @click="counter++" class="border-2 border-dashed p-5 outline-none opacity-20 hover:opacity-100 hover:border-solid">Compteur: {{counter}}</button>
</div>

<!--
- Ici, `count` est une variable réactive.
- Quand `count` change, Svelte met à jour automatiquement le DOM.
- Pas besoin de gérer manuellement les mises à jour du DOM !
-->

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

---

# 🪄 Runes

Les runes sont des mot-clefs utilisés dans la syntaxe de Svelte

<!-- - Fonctions prefixes par un `$`  -->
<!-- - Seulement présentes dans la <span class="text-orange-600">version 5</span> -->

<div class="mt-4 space-y-8">
<div class="grid grid-cols-5 items-end gap-0">
<div class="col-span-2">
    <code>$state</code> crée une variable <i>réactive</i> (l'UI va reagir aux changements de cette variable)
</div>
<div class="col-span-2 col-start-4">
```svelte
<script>
let message = $state('hello');
</script>
```
</div>
</div>

<div v-click class="grid grid-cols-5 items-end gap-0">
<div class="col-span-2">
    <code>$derived</code> utilisée pour créer des valeurs <i>dérivées</i> qui réagissent aux changements de leurs dépendances
</div>
<div class="col-span-2 col-start-4">
```svelte
<script>
let message = $state('hello');
let messageLength = $derived(message.length)
</script>
```
</div>
</div>

<div v-click class="grid grid-cols-5 items-end gap-0">
<div class="col-span-2">
    <code>$props</code> utilisée pour déclarer et accéder aux propriétés d'un composant
</div>
<div class="col-span-2 col-start-4">
```svelte
<script>
const {propNum1, propNum2} = $props()
</script>
```
</div>
</div>

</div>

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

---
layout: two-cols
---

# 🧑🏽‍💻 Coding time

<img class="mt-12 w-40 h-40" src="/pepegaHackerman.gif" alt="pepega_hacker" />

::right::

# Pré-requis

- Connaissance de base en HTML et CSS
- Familier avec JavaScript
- Node.js dans votre machine
- Un éditeur de texte

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

---

# 📋 Svelte + Todo


<SlidevVideo class="w-auto h-92 mx-auto mt-8" controls>
    <source src="/screencast-todo.mp4" type="video/mp4" />
    <p>Votre navigateur ne supporte pas les vidéos 😢. Toutefois vous pouvez la télécharger <a href="/screencast-todo.mp4">ici</a>.</p>
</SlidevVideo>

<div class="my-[2rem] mx-[3.5rem] abs-bl text-xl">
<span class="text-orange-600">{{ $nav.currentPage }}</span> |
{{ $slidev.configs.title }}
</div>

---
layout: two-cols
---

# 📋 Svelte + Todo

1. Installer les dépendances avec `npm install`
2. Ouvrir le projet sur votre editeur
3. Visualiser le project avec `npm run dev`
4. Visiter `http://localhost:5173` sur votre navigateur

::right::

<SlidevVideo class="w-full h-auto" controls>
    <source src="/screencast-steps.webm" type="video/webm" />
    <p>Votre navigateur ne supporte pas les vidéos 😢. Toutefois vous pouvez la télécharger <a href="/screencast-steps.webm">ici</a>.</p>
</SlidevVideo>

---
layout: image-right
image: /app-filetree.png
backgroundSize: contain
---

# 📋 Svelte + Todo

1. Ouvrir `+page.svelte`
2. Ajouter ces lines 👇🏿 dans le `<script` tag

<br />

```svelte {4-7,1,8}
<script>
  import '../app.css';

  let todos = $state([
    {id: '1', title: 'Item #1', completed: false },
    {id: '2', title: 'Item #2', completed: false },
  ])
</script>
```

<br />

> Ici nous avons créer une variable réactive avec `$state()` et nous allons l'utiliser dans notre markup HTML.

---

# 📋 Svelte + Todo

- Selectionnez tout le contenu de la balise `<ul class="todo__list">`
- Supprimez tout
- Remplacer par ce bout de code

---

# 📋 Svelte + Todo

```svelte {*|2,21|*}
<ul class="todo__list">
    {#each todos as todo, i (todo.id)}
        <li class="todo__list__item">
            <label>
                <input bind:checked={todos[i].completed} type="checkbox" id="todo-{todo.id}" name="todo-{todo.id}" />
                <span>{todo.title}</span>
            </label>
            <button aria-label="Supprimer todo">
                <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
                    <path
                        fill="none"
                        stroke="currentColor"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M3 6h18m-2 0v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6m3 0V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2m-6 5v6m4-6v6"
                    />
                </svg>
            </button>
        </li>
    {/each}
</ul>
```

---

# 📋 Svelte + Todo

- Ajout de la fonction `addTodo()`
- Utilisation de [crypto.randomUUID()](https://developer.mozilla.org/en-US/docs/Web/API/Crypto/randomUUID) pour générer des IDs

```svelte
<script>
  function addTodo (e) {
    if (e.key === 'Enter') return

    todos.push({ id: crypto.randomUUID(), title: e.target.value, completed: false })

    e.target.value = ''
  }
</script>
```

<br />

- Utilisation de l'event [keydown](https://developer.mozilla.org/en-US/docs/Web/API/Element/keydown_event)

```svelte
<header class="todo__header">
    <input
        onkeydown={addTodo}
        placeholder="Ajouter une todo"
        type="text" />
</header>
```

---

# 📋 Svelte + Todo

- Ajout de la fonction `deleteTodo(id)`

```svelte
<script>
  function addTodo (id) {
    todos = todos.filter(todo => todo.id !== id)
  }
</script>
```

<br />

- Utilisation de l'event [click](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event) sur le `button`

```svelte
<button onclick={() => deleteTodo(todo.id)} aria-label="Supprimer todo">
    <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
        <path
            fill="none"
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M3 6h18m-2 0v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6m3 0V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2m-6 5v6m4-6v6"
        />
    </svg>
</button>
```

---

# 📋 Svelte + Todo

Pour le reste vous pouvez suivre ces liens

- Lien pour la solution [ici](https://github.com/GalsenDev221/svelte-todo)
- [Documentation officielle de Svelte](https://svelte.dev/docs/svelte/overview)
- [Tutoriel Svelte](https://svelte.dev/tutorial/svelte/welcome-to-svelte)

---
layout: end
---

<h1 class="animate-bounce">👏🏿 Merci de votre attention</h1>

<div class="abs-br m-6 flex gap-2">
  <a href="https://galsen.dev" target="_blank" alt="Galsen DEV website"  class="slidev-icon-btn opacity-50 !border-none !hover:opacity-100 !hover:bg-transparent">
    <galsen-icon />
  </a>
</div>
