<template>
  <div id="app">
    <Todo />
  </div>
  <!-- <div id="app">
    <h1>{{ msg }}</h1>
    <p v-if="isAwesome">Galvanize is AWESOME!!!</p>
    <p v-else>Galvanize is not awesome</p>
    <ul>
      <li v-for="poop of items" :key="poop">{{ poop }}</li>
    </ul>
    <p :class="{hideMe: isHidden}">Hide me</p>
  </div> -->
</template>

<script>
import Todo from './components/Todo.vue'

export default {
  name: 'App',
  components: {
    Todo
  },
  data () {
    return {
      msg: 'Hello Galvanize',
      isAwesome: false,
      items: ['poop', 'butt', 'hello'],
      isHidden: true
    }
  }
}
</script>

<style>
  .hideMe {
    display: none;
  }
</style>
