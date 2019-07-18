<template>
  <section class="alert" :aria-expanded="expanded">
    <article>
      <h2 class="alert-heading">{{ headline }}</h2>
      <div class="content" v-html="content"></div>
      <div class="cta">
        <a href="/">CTA Text Link</a>
        <button>CTA Button</button>
      </div>
    </article>
    <button class="close" @click.prevent="on_click_close">
      <span>Close</span>
      <span>Alert</span>
    </button>
  </section>
</template>

<script>
export default {
  name: "Alert",
  props: {
    headline: String,
    content: String
  },
  methods: {
    on_click_close: function(event) {
      this.expanded = !this.expanded;
    },
    collapse: function() {
      this.expanded = false;
    },
    expand: function() {
      this.expanded = true;
    }
  },
  data() {
    return {
      expanded: false
    };
  },
  mounted: function() {
    this.expand();
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$base-transition-duration: 195ms;
$base-transition-easing: cubic-bezier(0.4, 0, 0.2, 1);
@mixin transition(
  $property: all,
  $duration: $base-transition-duration,
  $easing: $base-transition-easing
) {
  -webkit-transition: $property $duration $easing;
  -moz-transition: $property $duration $easing;
  -ms-transition: $property $duration $easing;
  -o-transition: $property $duration $easing;
  transition: $property $duration $easing;
}
$alert-color: #666;
$alert-padding-y: 20px;
$alert-padding-x: 20px;
$cta-gutter: 20px;
.alert {
  @include transition(all, 250ms, cubic-bezier(0.4, 0, 1, 1));
  background: $alert-color;
  color: #fff;
  position: relative;
  overflow: hidden;
  max-height: 0;
  padding: 0 $alert-padding-x;

  &[aria-expanded="true"] {
    max-height: 100vh;
    overflow-y: auto;
    padding-top: $alert-padding-y;
    padding-bottom: $alert-padding-y;
  }
}
article {
  & > :first-child {
    margin-top: 0;
  }
  & > :last-child {
    margin-bottom: 0;
  }

  .cta {
    display: flex;
    justify-content: flex-end;
    margin-right: ($cta-gutter / 2) * -1;
    margin-left: ($cta-gutter / 2) * -1;
    & > * {
      margin-right: ($cta-gutter / 2);
      margin-left: ($cta-gutter / 2);
    }
  }
}

button.close {
  /* background: none; */
  /* border: none; */
  /* color: white; */
  position: absolute;
  top: $alert-padding-y;
  right: $alert-padding-x;
  /* text-transform: uppercase; */
  &:before {
    content: "\00d7";
    margin-right: 0.5em;
  }
  span {
    /* text-decoration: underline; */
  }
  &:hover {
    &:before,
    span {
      /* color: black; */
    }
  }

  span:nth-child(2) {
    position: absolute;
    top: -999em;
    left: -999em;
  }
}
</style>

