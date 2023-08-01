<template>
  <div class="ctr">
    <Question />
    <Result/>
    <button type="button" class="reset-btn">Reset</button>
  </div>
</template>

<script>
import Question from "./components/Question.vue";
import Result from "./components/Result.vue";
import quizData from "./data/data.js";

export default {
  name: "App",
  components: {
    Question,
    Result,
  },
  data() {
    return {
      questionAnswerd:0,
      question: quizData,
    };
  },
};
</script>

<style lang="scss"></style>
