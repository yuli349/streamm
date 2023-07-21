<template>
  <div class="wrapper">
    <Sidebar></Sidebar>
    <Header @add-information="submitQuestion"></Header>
    <main>
      <div v-for="(item, index) in arrAnswers" :key="index"
           class="arr-answers">
        <Answer :item="item"></Answer>
      </div>
    </main>
  </div>
</template>

<script>
import answers from "../../assets/answers.json";
import Vue from 'vue';

export default {
  name: 'Vacation',

  data() {
    return {
      answersList: [],
      arrAnswers: [],
      count: 0,
      elem: {},
      arr: [],
    }
  },

  components: {
    Sidebar: () => import('@/components/sidebar/Sidebar.vue'),
    Header: () => import('@/components/header/Header.vue'),
    Answer: () => import('@/components/answer/Answer.vue'),
  },

  mounted() {
    this.answersList = answers;
  },

  computed: {
  },

  methods: {
    submitQuestion(text) {
      this.answersList[this.count].text = text;
      this.arrAnswers.unshift(this.answersList[this.count]);
      this.count++;
    },
  }
}
</script>
