<template>
    <li>
        <button v-on:click="handleClickAnswerOption">{{ button_text }}</button>
    </li>
</template>

<script>
  export default {
    name: "QuizButton",
    props: ['button_text'],
    methods: {
      handleClickAnswerOption() {
        this.$parent.handleClickAnswerOption();
      },
    },
  };
</script>

<style scoped>
    button {
        padding: 10px 50px;
        margin: 5px;
    }
</style>
