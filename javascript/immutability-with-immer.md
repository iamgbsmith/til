# Immutability With Immer

__Category: JavaScript__

[Immer](https://github.com/immerjs/immer) is a library that facilitates easier state management in JavaScript. It helps you to create the next immutable state tree by simply modifying the current tree. Immer works by applying all your changes to a temporary draftState, which is a proxy of the currentState. Once all your mutations are completed, Immer will produce the nextState based on the mutations to the draft state.

If using Immer in a React project, add to your package dependencies as follows:

```
yarn add immer
```

Include the `produce` method for basic operations:

```javascript
import {produce} from 'immer';
```

Assuming an array of objects with the following structure:

```javascript
const todosArray = [
  { id: "id1", done: false, body: "Clean the car" },
  { id: "id2", done: false, body: "Mow the lawns" }
];
```
  
Add an item:

```javascript
const addedTodosArray = produce(todosArray, draft => {
  draft.push({ id: "id3", done: false, body: "Book holiday" });
});
```

Remove an item:

```javascript
const deletedTodosArray = produce(todosArray, draft => {
  draft.splice(draft.findIndex(todo => todo.id === "id1"), 1);
});
```

Update an item:

```javascript
const updatedTodosArray = produce(todosArray, draft => {
  draft[draft.findIndex(todo => todo.id === "id1")].done = true;
});
```

See [Introduction to Immer](https://immerjs.github.io/immer/docs/introduction) for more details.
