<template>
  <div id="app" :class="{ fancy: default_css }">
    <PlaceholderPage></PlaceholderPage>
    <AlertControlPanel @toggle-style="toggle_style"></AlertControlPanel>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
import PlaceholderPage from "./components/PlaceholderPage";
import AlertControlPanel from "./components/AlertControlPanel";

export default {
  name: "App",
  components: {
    PlaceholderPage,
    AlertControlPanel
  },
  data() {
    return {
      default_css: true
    };
  },
  methods: {
    toggle_style: function(payload) {
      console.log("le bar", payload);
      this.default_css = payload;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 0;
  padding: 0;
  /* margin-top: 60px; */
}
</style>
