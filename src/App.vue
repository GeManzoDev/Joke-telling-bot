<template>
  <ListenJoke></ListenJoke>
  <SocialBar></SocialBar>
</template>

<script>
import ListenJoke from './components/Listen-joke.vue';
import ChoseLanguageDropdown from './components/Chose-language-dropdown.vue';
import SocialBar from './components/Social-bar.vue';
export default {
  name: 'App',
  components: { ListenJoke, ChoseLanguageDropdown, SocialBar },
};
</script>

<style>
* {
  font-family: 'Architects Daughter', cursive;
  background-color: #f8f6f4;
}
</style>
