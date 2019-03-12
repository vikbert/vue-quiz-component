<template>
    <main>
        <section><p>{{question.instruction_text}}</p></section>
        <section className="button">
            <ul>
                <QuizButton v-for="option in question.answer_options"
                            :key="option.id"
                            :button_text="option">
                </QuizButton>
            </ul>
        </section>
    </main>
</template>

<script>
  import QuizButton from './QuizButton';

  export default {
    name: "QuizQuestion",
    props: ['question'],
    components: {
      QuizButton,
    },
    methods: {
      handleClickAnswerOption() {
        this.$parent.incrementQuestionIndex();
      },
    },
  };
</script>

<style scoped>
    ul {
        list-style: none;
    }
</style>
