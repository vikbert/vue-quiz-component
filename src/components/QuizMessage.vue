<template>
    <section :class="{ 'error': is_invalid_answer, 'success': is_quiz_reset }">{{ message }}</section>
</template>

<script>
  export default {
    name: "QuizMessage",
    props: ['is_invalid_answer', 'is_quiz_reset', 'message'],
  };
</script>

<style scoped>
    .info, .success, .warning, .error, .validation {
        border: 1px solid;
        margin: 10px 0px;
        padding: 15px 10px 15px 50px;
        background-repeat: no-repeat;
        background-position: 10px center;
    }

    .success {
        color: #4F8A10;
        background-color: #DFF2BF;
    }

    .error {
        color: #D8000C;
        background-color: #FFBABA;
    }
</style>
