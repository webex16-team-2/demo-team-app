<template>
  <h1>赤めのVueパレット</h1>
  <div class="app">
    <div
      class="palette"
      v-on:mousemove="changeColor"
      v-on:click="fetchColor"
      v-bind:style="palletStyle"
    ></div>
    <p>rgba( 150, {{ green }}, {{ blue }}, 0.5 )</p>
    <div class="colors-container">
      <div
        class="mini-palette"
        v-for="color in colors"
        :key="color.id"
        v-bind:style="{
          backgroundColor: `rgba(150, ${color.green},${color.blue}, 0.5)`,
        }"
        v-on:click="showColor(color)"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      green: 0,
      blue: 0,
      colors: [
        //色のデータが並ぶ
      ],
    }
  },
  methods: {
    changeColor(e) {
      this.green = e.offsetX
      this.blue = e.offsetY
    },
    fetchColor() {
      const newColor = {
        green: this.green,
        blue: this.blue,
      }
      this.colors.push(newColor)
    },
    showColor(color) {
      this.green = color.green
      this.blue = color.blue
    },
  },
  computed: {
    palletStyle() {
      return {
        backgroundColor: `rgba(150,${this.green}, ${this.blue}, 0.5)`,
      }
    },
  },
}
</script>

<style>
h1 {
  text-align: center;
}
.app {
  display: flex;
  width: 100%;
  flex-direction: column;
  align-items: center;
}
.palette {
  width: 255px;
  height: 255px;
}
.mini-palette {
  min-width: 60px;
  height: 60px;
}
.colors-container {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  padding-top: 8px;
}
</style>
