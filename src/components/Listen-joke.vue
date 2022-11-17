<template>
  <div class="container">
    <img class="funny-kid" src="../assets/Standing.png" alt="" />
    <div class="bubble">
      <img
        v-show="hearJoke"
        class="bubble-cloud"
        src="../assets/v999-14.jpg"
        alt=""
      />
      <div v-if="hearJoke" class="joke">
        {{ joke }}
      </div>
    </div>
    <h3>Hey, wanna hear a joke?</h3>
    <button @click="tellAJoke" class="btn">{{ callToAction }}</button>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Listen-joke',
  data() {
    return {
      hearJoke: false,
      callToAction: 'Hear a joke!',
      joke: '',
      lang: '',
    };
  },
  methods: {
    async tellAJoke() {
      // fetching api
      let res = await axios.get(
        'https://official-joke-api.appspot.com/jokes/random',
        {
          params: {
            setup: '',
            punchline: '',
          },
        }
      );
      console.log(res.data);
      console.log((res.data.setup + ' ' + res.data.punchline).length);
      // checking for joke length because cloud is small
      if ((res.data.setup + ' ' + res.data.punchline).length > 75) {
        // if too long make another request
        let result = await axios.get(
          'https://official-joke-api.appspot.com/jokes/random'
        );
        console.log(result.data);
        this.joke = result.data.setup + ' ' + result.data.punchline;
        console.log(this.joke.length);
      }
      //    if short enough keep the first joke
      else {
        this.joke = res.data.setup + ' ' + res.data.punchline;
      }
      // pop up the cloud
      this.hearJoke = true;
      // change the button text
      this.callToAction = 'Hear another joke!';
      this.speakTheJoke(this.joke);
    },
    speakTheJoke(el) {
      const voice = window.speechSynthesis;
      const voices = voice.getVoices();
      const utterThis = new SpeechSynthesisUtterance(el);
      utterThis.pitch = 10;
      utterThis.lang = this.lang;
      voice.speak(utterThis);
      console.log(voices);
    },
  },
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
  font-size: 12px;
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
