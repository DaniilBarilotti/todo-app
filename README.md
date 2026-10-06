# To-do App

A React and TypeScript task manager with REST-backed task operations.

[Live demo](https://daniilbarilotti.github.io/todo-app/) · [Portfolio](https://daniilbarilotti.github.io/Portfolio/)

## Features

- Create, edit, delete and complete tasks.
- All / active / completed views.
- Loading and error feedback for asynchronous operations.
- Reusable typed task components and a dedicated editing hook.

## Stack

React · TypeScript · SCSS · REST API · Vite / Mate Academy scripts.

## Run locally

```bash
git clone https://github.com/DaniilBarilotti/todo-app.git
cd todo-app
npm ci
npm start
```

`npm run build` creates the bundle. Installation runs the existing Mate scripts update and Cypress verification hooks; those tools require a compatible local environment.

## Data and architecture

`src/api/todos.ts` defines task requests. `src/utils/fetchClient.ts` sends GET, POST, PATCH and DELETE requests to `https://mate.academy/students-api`. Components handle rendering; `src/components/hooks/useTodo.ts` manages editing, completion and deletion flows.

Task persistence depends on the external learning API. This is not a localStorage-only application and does not include its own backend or authentication service.

## Project scope

Learning project based on the Mate Academy starter tooling. Availability of the hosted demo depends on the external API. The presence of Cypress dependencies is not evidence of a passing test suite; tests and builds must be run in a compatible environment before release.

## Engineering discussion

Trimming an edited title prevents blank task labels; an empty title follows the deletion flow. Failed updates keep the editor focused for retry. Next improvements include descriptive HTTP errors, request cancellation and clearer API configuration.
