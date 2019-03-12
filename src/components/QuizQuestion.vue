<template>
    <main>
        <section><h2>{{question.instruction_text}}</h2></section>
        <QuizMessage v-if="incorrectAnswer"
                     :is_invalid_answer="incorrectAnswer"
                     message="Sorry, the answer was not correct.">
        </QuizMessage>
        <section className="button">
            <ul>
                <QuizButton v-for="option in question.answer_options"
                            :key="option.id"
                            :button_text="option">
                </QuizButton>
            </ul>
        </section>
        <br>
    </main>
</template>

<script>
  import QuizButton from './QuizButton';
  import QuizMessage from './QuizMessage';

  export default {
    name: "QuizQuestion",
    data() {
      return {
        incorrectAnswer: false,
        error_message_class: 'error',
        success_message_class: 'success',
      };
    },
    props: ['question'],
    components: {
      QuizButton,
      QuizMessage,
    },
    methods: {
      handleClickAnswerOption(button_text) {
        if (button_text === this.question.answer) {
          this.$parent.incrementQuestionIndex();
          this.incorrectAnswer = false;
        } else {
          this.incorrectAnswer = true;
        }
      },
    },
  };
</script>

<style scoped>
    ul {
        list-style: none;
    }
</style>
