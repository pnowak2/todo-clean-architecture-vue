<template>
  <div>
    <section class="todoapp">
      <todo-header @addItem="onAddItem($event)"></todo-header>
      <todo-item></todo-item>
      <todo-footer></todo-footer>
    </section>

    <!-- <section class="todoapp">
      <header class="header">
        <h1>todos</h1>
        <input class="new-todo" placeholder="What needs to be done?" autofocus />
      </header>

      <section class="main">
        <input class="toggle-all" id="toggle-all" type="checkbox" />
        <label for="toggle-all">Mark all as complete</label>
        <ul class="todo-list">
          <li v-for="todo in todos" v-bind:key="todo.id">
            <div class="view">
              <input class="toggle" type="checkbox" />
              <label>{{ todo.name }}</label>
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
    </section> -->

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

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';
import TodoHeader from './components/TodoHeader.vue';
import TodoItem from './components/TodoItem.vue';
import TodoFooter from './components/TodoFooter.vue';

@Component({
  components: { TodoHeader, TodoItem, TodoFooter }
})
export default class App extends Vue {
  onAddItem(name: string) {
    console.log('add item', name);
  }
}
</script>