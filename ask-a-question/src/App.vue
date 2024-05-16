<template>
  <div class="container">
    <component :is="screens[position]" @goto="handleGoTo"></component>
  </div>
</template>

<script>
import appInitial from './components/initial.vue';
import appConfirm from './components/confirm.vue';
import appResults from './components/results.vue';

export default {
  components: {
    appInitial,
    appConfirm,
    appResults
  },
  data() {
    return {
      screens: ['appInitial', 'appConfirm', 'appResults'],
      position: 0
    }
  },
  methods: {
    handleGoTo(position) {
      this.position = position;
    }
  }
}
</script>

<style>
@import './assets/style.css';
</style>
