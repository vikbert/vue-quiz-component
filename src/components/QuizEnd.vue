<template>
    <div className='quiz-end'>
        <QuizMessage v-if="is_quiz_reset"
                     :is_quiz_reset="is_quiz_reset"
                     message="Quiz is going to be reset ......">
        </QuizMessage>
        <p>Thanks for playing!</p>
        <a href="#" v-on:click="handleClick">Reset Quiz</a>
    </div>
</template>

<script>
  import QuizMessage from './QuizMessage';

  export default {
    name: "QuizEnd",
    data() {
      return {
        is_quiz_reset: false,
      };
    },
    props: ['resetQuestionIndexHandler'],
    components: {
      QuizMessage,
    },
    methods: {
      handleClick() {
        this.is_quiz_reset = true;
        setTimeout(() => {
          this.resetQuestionIndexHandler();
        }, 800);
      },
    },
  };
</script>

<style scoped>

</style>
