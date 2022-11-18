<template>
  <h1>Home</h1>
  <div class="firstblock">
    <router-link
        to="/quiz"
        class="vuelink"
        exact-active-class="vuelink--exact-active"
        >Vue クイズ</router-link
      >
      </div>
  <div class="secondblock">
      <router-link
        to="/palette"
        class="vuelink"
        exact-active-class="vuelink--exact-active"
        >Vue パレット</router-link
      >
      </div>
  <div class="thirdblock">
      <router-link
        to="/memo"
        class="navigation__link"
        exact-active-class="navigation__link--exact-active"
        >Vue メモ</router-link
      ></div>
</template>

<style scoped>
.firstblock{
  height: 300px;
  background-color: #ddd;
  font-size: 60px;
  font-family: serif;
  display: flex;
  justify-content: center;
  align-items: center;
}
.secondblock {
  height: 300px;
  background-color: #f0f0f0;
  font-size: 60px;
  font-family: serif;
  display: flex;
  justify-content: center;
  align-items: center;
  
}

.thirdblock {
  height: 300px;
  background-color: #f05f40;
  font-size: 60px;
  font-family: serif;
  display: flex;
  justify-content: center;
  align-items: center;
  
}
</style>
