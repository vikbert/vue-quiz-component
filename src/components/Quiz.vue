<template>
    <div>
        <QuizEnd v-if="isQuizEnd()" :resetQuestionIndexHandler="resetQuestionIndex"></QuizEnd>
        <QuizQuestion v-else :question="quiz_data.quiz_questions[quiz_position - 1]"></QuizQuestion>
    </div>
</template>

<script>
  import QuizQuestion from './QuizQuestion.vue'
  import QuizEnd from './QuizEnd.vue'
  import json from './quiz_data.json'

  export default {
    name: "Quiz",
    data() {
      return {
        quiz_data: json,
        quiz_position: 1,
        quiz_length: json.quiz_questions.length
      }
    },
    components: {
      QuizQuestion,
      QuizEnd
    },
    methods: {
      resetQuestionIndex() {
        this.quiz_position = 1
      },
      incrementQuestionIndex() {
        this.quiz_position += 1
      },
      isQuizEnd() {
        return (this.quiz_position - 1) === this.quiz_length
      },
    },
  };
</script>

<style scoped>
</style>
