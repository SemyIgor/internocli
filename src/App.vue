<template>
  <div id="app">
    <div class="outer-shell">
      <ProjectPage />
    </div>
  </div>
</template>

<script>
import ProjectPage from './pages/ProjectPage.vue';

export default {
  name: 'App',
  components: {
    ProjectPage
  },
  data() {
    return {
    }
  },
  methods: {
  },
}
</script>

<style lang="scss">
@import "@/assets/scss/variables";
@import "@/assets/scss/extends";

*,
*::after,
*::before {
  // box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html {
  font-size: calc(100% / 16 * 10);
}

#app {
  a {
    text-decoration: none;
  }

  h1 {
    margin: 0;
  }

  font-family: 'Jost',
  sans-serif;
  font-style: normal;
  font-weight: 400;
  line-height: 1.25;
  background-color: #F4F0EC;
}

.outer-shell {
  margin: 0 auto;
  overflow: hidden;
  background-color: #ffffff;
  // background-color: #F4F0EC;
  padding-left: 16px;
  padding-right: 16px;
  max-width: 1920px;
}

.center {
  padding-left: calc(50% - $siteContentWidth / 2);
  padding-right: calc(50% - $siteContentWidth / 2);
}
</style>
