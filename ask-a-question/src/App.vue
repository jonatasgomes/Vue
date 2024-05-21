<template>
  <div class="container">
    <transition name="fade" appear mode="out-in">
      <component
        :is="screens[position]"
        :question="question"
        :result="result"
        @goto="handleGoTo"
        @question="handleQuestion"
        @showResult="showResult"
        @startOver="startOver"
        @handleToast="handleToast"
      />
    </transition>
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
      position: 0,
      question: '',
      result: '',
      list: ['Yes', 'No', 'Maybe', 'Not sure..try again', 'Ask a friend', 'Call the police']
    }
  },
  methods: {
    handleGoTo(position) {
      this.position = position;
    },
    handleQuestion(question) {
      this.question = question;
    },
    showResult() {
      let item;
      do {
        item = this.list[Math.floor(Math.random() * this.list.length)];
      } while (item == this.result);
      this.result = item;
    },
    startOver() {
      this.position = 0;
      this.question = '';
      this.result = '';
    },
    handleToast(config) {
      this.$toast.show(config.message, {
        type: config.type,
        position: 'bottom',
        duration: 2000
      });
    }
  }
}
</script>

<style>
@import './assets/style.css';
.fade-enter-from {
  opacity: 0;
}
.fade-enter-active {
  transition: 0.5s;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: 0.5s;
}
.fade-leave-to {
  opacity: 0;
}
</style>

<!-- https://ask-question-decide-it.surge.sh/ -->
