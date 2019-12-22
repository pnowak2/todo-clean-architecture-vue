<template>
  <footer class="footer">
    <span class="todo-count">
      <strong>{{ count }}</strong> item(s) left
    </span>

    <ul class="filters">
      <li>
        <a href="#/" :class="{ selected: filter === 'all' }" @click="onShowAll">All</a>
      </li>
      <li>
        <a href="#/" :class="{ selected: filter === 'active' }" @click="onShowActive">Active</a>
      </li>
      <li>
        <a href="#/" :class="{ selected: filter === 'completed' }" @click="onShowCompleted">Completed</a>
      </li>
    </ul>

    <button class="clear-completed" @click="onClearCompleted">Clear completed</button>
  </footer>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class extends Vue {
  @Prop() private filter!: string;
  @Prop() private count!: number;

  onShowAll() {
    this.$emit('all')
  }

  onShowActive() {
    this.$emit('active')
  }

  onShowCompleted() {
    this.$emit('completed')
  }

  onClearCompleted() {
    this.$emit('clearCompleted')
  }
}
</script>
