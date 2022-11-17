<template>
  <h1>Vue クイズ</h1>
  <div class="app">
    <h2>Q. {{ quiz.text }}</h2>
    <img
      class="quiz-image"
      src="https://via.placeholder.com/300x300"
      v-bind:alt="quiz.text"
    />
    <div class="container">
      <button
        v-for="(choice, i) in quiz.choices"
        v-bind:key="i"
        v-on:click="choiced(choice)"
      >
        {{ choice.text }}
      </button>
    </div>
    <div>{{ feedback }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      feedback: "",
      quiz: {
        text: "1868年～1912年の元号はなんでしょう",
        choices: [
          {
            text: "江戸",
            isCorrect: false,
            feedback:
              "残念！江戸時代は1603年から1868年です",
          },
          {
            text: "明治",
            isCorrect: true,
            feedback:
              "正解！1868年から1912年は明治時代です",
          },
          {
            text: "大正",
            isCorrect: false,
            feedback:
            "残念！大正時代は1912年から1926年です",
          },
        ],
      },
    }
  },
 methods: {
   choiced(choice){
    this.feedback = choice.feedback
   },
 },
}

</script>

<style>
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.quiz-image {
  height: 300px;
  width: 300px;
  object-fit: contain;
}

.container {
  display: flex;
  height: 2em;
  width: 300px;
  padding: 1em;
  justify-content: space-around;
}
</style>
