<template>
  <div class="questions-ctr">
    <div class="progress">
      <div class="bar"></div>
      <div class="status">1 out of 3 questions answered</div>
    </div>
    <div
      class="single-question"
      v-for="(question, qi) in questionLists"
      :key="question.q"
      v-show="questionAnswerdLists === qi"
    >
      <div class="question">{{ question.q }}</div>
      <div class="answers">
        <div
          class="answer"
          v-for="answer in question.answers"
          :key="answer.text"
          @click.prevent="selectAnswer(answer.is_correct)"
        >
          {{ answer.text }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Questions",
  props: ['questionLists',"questionAnswerdLists"],
  emits:["question_answerd"],
  methods: {
    selectAnswer(is_correct) {
      this.$emit("question_answerd", is_correct);
    },
    
  },
};
</script>

<style lang="scss" scoped></style>
