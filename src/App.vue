<template>
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
</template>

<style>
@import "../node_modules/todomvc-app-css/index.css";
@import "../node_modules/todomvc-common/base.css";
</style>
