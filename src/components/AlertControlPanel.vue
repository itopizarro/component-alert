<template>
  <aside>
    <h2>Alert Control Panel</h2>
    <p>for demonstration purposes</p>
    <table>
      <tr>
        <th>Apply Style</th>
        <td>
          <button @click.prevent="toggle_style" v-text="( default_css ) ? 'Off' : 'On'"></button>
        </td>
      </tr>
      <tr v-if="alert_closed">
        <th>Reset Alert</th>
        <td>
          <button @click.prevent="reset_alert">Reveal Alert</button>
        </td>
      </tr>
    </table>
  </aside>
</template>

<script>
export default {
  name: "AlertControlPanel",
  props: {},
  methods: {
    toggle_style: function(event) {
      console.log("toggle_style");
      this.default_css = !this.default_css;
      this.$emit("toggle-style", this.default_css);
    },
    alert_close: function(event) {
      this.alert_closed = true;
    }
  },
  data() {
    return {
      default_css: true,
      alert_closed: false
    };
  },
  mounted: function() {}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
aside {
  position: fixed;
  bottom: 0;
  left: 50%;
  transform: translate(-50%, 0);
  padding: 20px;
  background-color: rgba(black, 0.666);
  color: white;
  & > :first-child {
    margin-top: 0;
  }
  & > :last-child {
    margin-bottom: 0;
  }
}
</style>

