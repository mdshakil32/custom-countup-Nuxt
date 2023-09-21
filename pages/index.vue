<template>
  <div class="wrapper-div">
    <h1>Custom Counter using Nuxt 3</h1>
    <h2>Intersection Observer || Interval</h2>
    <div class="pb-50">
      <CountUp count="100" />
    </div>
    <div class="pb-50">
      <CountUp count="200" />
    </div>
    <div class="pb-50">
      <CountUp count="300" />
    </div>
    <div class="pb-50">
      <CountUp count="400" />
    </div>
    <div class="pb-50">
      <CountUp count="500" />
    </div>
    <div class="pb-50">
      <CountUp count="600" />
    </div>
    <div class="pb-50">
      <CountUp count="700" />
    </div>
    <div class="pb-50">
      <CountUp count="800" />
    </div>
  </div>
</template>
<style scoped>
* {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  overflow: hidden;
}
.wrapper-div {
  overflow: hidden;
}
h1 {
  color: rgb(84, 84, 84);
}
h2 {
  color: grey;
}
.pb-50 {
  padding-bottom: 50px;
}
</style>
