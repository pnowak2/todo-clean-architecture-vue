<template>
  <header class="header">
    <h1>todo</h1>
    <input 
      v-model="name"
      type="text"
      class="new-todo" 
      placeholder="What needs to be done?" 
      autofocus="" 
      @keyup.enter="onAddItem">

      <input 
        id="toggle-all" 
        class="toggle-all" 
        type="checkbox"
        v-model="isToggleAll"
        @change="onToggleAllChange">
      <label for="toggle-all">
        Mark all as complete
      </label>
  </header>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class extends Vue {
  name: string = '';
  isToggleAll: boolean = false;

  onAddItem() {
    this.$emit('addItem', this.name);
    this.name = '';
  }

  onToggleAllChange() {
    if (this.isToggleAll) {
      this.$emit('toggleAllCompleted');
    } else {
      this.$emit('toggleAllActive');
    }
  }
}
</script>

<style lang="css" scoped>
.toggle-all + label {
    top: 14px;
}
</style>
