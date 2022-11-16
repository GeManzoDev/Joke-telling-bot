<template>
  <div class="container">
    <img class="funny-kid" src="../assets/Standing.png" alt="" />
    <div class="bubble">
      <img class="bubble-cloud" src="../assets/v999-14.jpg" alt="" />
      <div class="joke">
        Lorem ipsum dolor sit amet lorem Lorem ipsum dolor sit amet consectetur,
      </div>
    </div>
    <h3>Hey wanna hear a joke?</h3>
    <button class="btn">Hear a joke!</button>
  </div>
</template>

<script>
export default {
  name: 'Listen-joke',
};
</script>

<style scooped>
.container {
  top: 30px;
  width: 50vw;
  height: auto;
  text-align: center;
  position: relative;
  margin: auto;
}
.container h3 {
  font-size: 30px;
}

.funny-kid {
  text-align: center;
  margin: auto;
}
.bubble {
  position: absolute;
  display: flex;
  top: -58px;
  left: 450px;
  width: 250px;
  height: auto;
}
.bubble-cloud {
  width: 100%;
  height: auto;
}
.joke {
  font-size: 10px;
  position: relative;
  left: -220px;
  top: 90px;
  background-color: transparent;
  min-width: 70%;
  padding: 5px;
}
.btn {
  border-radius: 6px;
  padding: 3px 5px;
  font-size: 18px;
  cursor: pointer;
  background-image: radial-gradient(
      circle at 49.45% 10.73%,
      #ff8008,
      transparent 100%
    ),
    radial-gradient(circle at 87.88% 94.1%, #ffc837, transparent 100%),
    radial-gradient(circle at 50% 50%, #ffffff, #ffffff 100%);
}
.btn:hover {
  transform: scale(0.97);
}
</style>
