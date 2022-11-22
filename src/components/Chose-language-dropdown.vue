<template>
  <div class="language-picker">
    <form action="" class="language-picker__form">
      <label for="language-picker-select">Select your language</label>

      <select
        @change="getLanguage"
        name="language-picker-select"
        id="language-picker-select"
      >
        <option
          v-for="language in languages"
          :lang="language.name"
          :value="language.value"
          :id="language.id"
        >
          {{ language.value }}
        </option>
      </select>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Chose-language-dropdown',
  data() {
    return {
      languages: [
        {
          name: 'en',
          value: 'English',
          id: 1,
        },
        {
          name: 'de',
          value: 'Deutsch',
          id: 2,
        },
        {
          name: 'es',
          value: 'Espanol',
          id: 3,
        },
        {
          name: 'cs',
          value: 'Czech',
          id: 4,
        },
      ],
      selectedLang: 'en',
    };
  },
  methods: {
    getLanguage() {
      this.$emit('getLanguage');
    },
  },
  props: {
    joke: 'String',
  },
};
</script>

<style scoped>
.language-picker {
  position: absolute;
  right: 100px;
  padding: 5px;
}
#language-picker-select {
  margin-left: 10px;
}
</style>
