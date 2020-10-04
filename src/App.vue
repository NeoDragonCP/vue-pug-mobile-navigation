<template lang="pug">
#app
  NavigationMobile
  div(class="content", :class="{'open':showNav}")
    .top-bar
      i.fas.fa-bars#navigation-icon(v-if="mobileView && !showNav",@click="showNav = !showNav")
      i.fas.fa-times#navigation-icon(v-if="mobileView && showNav",@click="showNav = !showNav")
      Navigation(v-if="!mobileView")
    Content
</template>

<script>
import Navigation from "./components/Navigation";
import NavigationMobile from "./components/NavigationMobile";
import Content from "./components/Content";

export default {
  name: "App",
  data: function() {
    return {
      mobileView: false,
      showNav: false,
    };
  },
  methods: {
    handleView() {
      this.mobileView = window.innerWidth <= 768;
    },
  },
  created() {
    this.handleView();
    window.addEventListener("resize", this.handleView);
  },
  watch: {
    mobileView: function(val) {
      if (val === false) this.showNav = false;
    },
  },
  components: {
    Navigation,
    NavigationMobile,
    Content,
  },
};
</script>

<style lang="scss">
* {
  font-size: 1rem;
}
body {
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  font-family: "Segoe UI", Tahoma;
  background-color: #7ca971;
}
#app {
  position: relative;
  width: calc(100% - 20px);
  height: calc(100vh - 20px);
  padding: 10px;
  color: #333;

  overflow: hidden;
}
.top-bar {
  display: flex;
  width: 100%;
}
#navigation-icon {
  padding: 10px 10px 20px;
  margin-right: 10px;
  cursor: pointer;
  font-size: 2rem;
}
.content {
  position: absolute;
  top: 10px;
  width: calc(100% - 60px);
  height: calc(100vh - 60px);
  padding: 20px;
  background-color: #fff;
  border-radius: 30px;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  transition: 0.3s transform cubic-bezier(0, 0.12, 0.14, 1);
}
.open {
  transform: translateX(300px);
}
</style>
