<template>
    <div className='quiz-end'>
        <p>Thanks for playing!</p>
        <a href="#" v-on:click="handleClick">Reset Quiz</a>
    </div>
</template>

<script>
  export default {
    name: "QuizEnd",
    props: ['resetQuestionIndexHandler'],
    methods: {
      handleClick() {
        this.resetQuestionIndexHandler()
      }
    },
  };
</script>

<style scoped>

</style>
