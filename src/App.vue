<template>
  <div>
    <section class="todoapp">
      <header class="header">
        <h1>todos</h1>
        <input class="new-todo" placeholder="What needs to be done?" autofocus />
      </header>

      <section class="main">
        <input class="toggle-all" id="toggle-all" type="checkbox" />
        <label for="toggle-all">Mark all as complete</label>
        <ul class="todo-list">
          <li>
            <div class="view">
              <input class="toggle" type="checkbox" />
              <label>test</label>
              <button class="destroy"></button>
            </div>
            <input class="edit" value="test" />
          </li>
        </ul>
      </section>

      <footer class="footer">
        <span class="todo-count">
          <strong>3</strong> items left
        </span>
        <ul class="filters">
          <li>
            <a class="selected" href="#/">All</a>
          </li>
          <li>
            <a href="#/active">Active</a>
          </li>
          <li>
            <a href="#/completed">Completed</a>
          </li>
        </ul>
      </footer>
    </section>

    <footer class="info">
      <p>Double-click to edit a todo</p>
      <p>Written by <a href="mailto:piotr-andrzej.nowak@ext.ec.europa.eu">Piotr Nowak</a></p>
      <p>Part of <a href="http://todomvc.com">TodoMVC</a></p>
    </footer>
  </div>
  </template>

<style>
@import "../node_modules/todomvc-app-css/index.css";
@import "../node_modules/todomvc-common/base.css";
</style>

<script>
import { Component, Prop, Vue } from 'vue-property-decorator';
import { TodoPresenter, TodoDefaultPresenter, TodoRepository, TodoInMemoryRepository } from '@domisoft/todo-clean-architecture';

@Component
export default class App extends Vue {
  mounted() {
    const todoApp = new TodoDefaultPresenter(new TodoInMemoryRepository([]));

    todoApp.todos$.subscribe(todos => {
      console.log('todos', todos);
    });

    todoApp.addTodo('foo');

    todoApp.getAllTodos();
  }
}
</script>