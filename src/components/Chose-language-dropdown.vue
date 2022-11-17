<template>
  <div class="language-picker js-language-picker">
    <form action="" class="language-picker__form">
      <label for="language-picker-select">Select your language</label>

      <select
        @change="getLanguage"
        name="language-picker-select"
        id="language-picker-select"
      >
        <option
          v-for="lang in languages"
          :lang="lang.name"
          :value="lang.value"
          :id="lang.id"
        >
          {{ lang.value }}
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
          name: 'fr',
          value: 'Français',
          id: 3,
        },
        {
          name: 'it',
          value: 'Italiano',
          id: 4,
        },
      ],
      selectedLang: 'English',
    };
  },
  props: {},
  methods: {
    getLanguage() {
      const language =
        document.querySelector('select').selectedOptions[0].value;
      this.selectedLang = language;
      console.log(this.selectedLang);
      // this.$emit('getLanguage', lang);
    },
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
