<template>
  <div id="app">
    <div class="emojis">
      <span v-if="userSaidYes" key="yes">👍</span>
      <span v-else-if="userSaidNo" key="no">👎</span>
      <span v-else key="undecided">👍👎</span>
    </div>

    <BaseRadioButtonGroup :options="decisions" v-model="selected" />
  </div>
</template>

<script>
import BaseRadioButtonGroup from "./components/BaseRadioButtonGroup";

export default {
  name: "App",
  components: {
    BaseRadioButtonGroup,
  },
  data: () => ({
    decisions: ["Yes", "No", "Undecided"],
    selected: "",
  }),
  computed: {
    userSaidYes() {
      return this.selected === "Yes";
    },
    userSaidNo() {
      return this.selected === "No";
    },
    userIsUndecided() {
      return this.selected === "Undecided";
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.emojis {
  margin-bottom: 40px;
}

span {
  font-size: 25px;
}
</style>
