<template>
  <div>
    <h3>Your answer is:</h3>
    <div class="viewer">{{ result }}</div>
    <div class="animate_animated animate__bounceIn animate__delay-5s">
      <hr/>
      <button class="btn" @click="getResult">Decide Again</button>
      <button class="btn" @click="startOver">Start Over</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ['result'],
  mounted() {
    this.getResult();
  },
  methods: {
    startOver() {
      this.$emit('startOver')
    },
    getResult() {
      this.$emit('showResult');
    }
  }
}
</script>