<template>
  <div class="home">
    <button class="btn" @click="decreaseCounter">-</button>
    <span class="counter">{{ count }}</span>
    <button class="btn" @click="increaseCounter">+</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: 10
    }
  },
  methods: {
    increaseCounter() {
      this.count++
    },
    decreaseCounter() {
      this.count--
    }
  }
}
</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}
.btn, .counter {
  font-size: 40px;
  margin: 0 10px;
}
</style>