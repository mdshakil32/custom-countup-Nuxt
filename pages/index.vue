<template>
  <div class="wrapper-div">
    <div class="inner-div">
      <h1>Custom Counter using Nuxt 3</h1>
      <h2>Intersection Observer || Interval</h2>
      <CountUp count="100" />
    </div>
  </div>
</template>
<style scoped>
* {
  font-family: Arial, Helvetica, sans-serif;
  text-align: center;
  overflow: hidden;
}
h1 {
  color: rgb(84, 84, 84);
}
h2 {
  color: grey;
}
.wrapper-div {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
.inner-div {
  width: fit-content;
  /* height: fit-content; */
}
</style>
