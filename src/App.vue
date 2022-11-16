<template>
  <ChoseLanguageDropdown></ChoseLanguageDropdown>
  <ListenJoke></ListenJoke>
</template>

<script>
import ListenJoke from './components/Listen-joke.vue';
import ChoseLanguageDropdown from './components/Chose-language-dropdown.vue';

export default {
  name: 'App',
  components: { ListenJoke, ChoseLanguageDropdown },
};
</script>

<style>
* {
  font-family: 'Architects Daughter', cursive;
  background-color: #f8f6f4;
}
</style>
