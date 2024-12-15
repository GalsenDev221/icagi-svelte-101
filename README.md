# Svelte: A fresh approach to web development

## Building a Todo app, step-by-step

Presented by *Papa Elhadj Abdoulaye NDOYE*

- **#1 tetris player** in the country
- frontend developer
- Admin Member of Galsen DEV

---

# What is Svelte

- a radical new approach to building user interfaces (UI)
- compiles your components into highly efficient JavaScript
- let's you write less code, do more
- ~no virtual DOM~ (this might be too technical for them)
- reactive programming made easy

---

# Comparison with other framworks

> [!NOTE]
> fill this later...

---

# Overview of the syntax

# Setting up the environment

- install **Node.js** and **npm**
- create a new svelte project

```bash
npx sv create todo-app
```

- basic project structure

```
├── package.json
├── README.md
├── src
│   ├── app.d.ts
│   ├── app.html
│   ├── lib
│   │   └── index.ts
│   └── routes
│       └── +page.svelte
├── static
│   └── favicon.pn/g
├── svelte.config.js
├── tsconfig.json
└── vite.config.ts
```

> [!INFO]
> Most of the magic happens in the `./src` folder, the rest is used by Svelte for configuration purposes.

---

# What we'll build

![app-mockup](./svelte-todo.png)

> [!DANGER]
> make the image and the text side-by-side

> [!INFO]
> transition into coding session.
