<template>
  <div @mouseenter="animate" @mouseleave="returnanimation">
    <div class="container_row">
      <div class="layer1">
        <div class="bg pa-16" :style="{ backgroundColor: color }" ref="bg">
          <div v-show="animating">
            <p class="font-weight-bold">{{ subtitle }}</p>
            <p class="font-weight-black">{{ title }}</p>
            <p>{{ text }}</p>
          </div>
        </div>
      </div>
      <div class="layer2">
        <div class="fg" ref="fg"><v-img :src="image"></v-img></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "subtitle", "color", "image", "text"],
  data: () => ({
    animating: false,
  }),
  methods: {
    animate() {
      this.animating = true;
      this.$refs.fg.style.maxWidth = `30%`;
      this.$refs.fg.style.maxHeight = `30%`;
      this.$refs.fg.style.top = `170%`;
      this.$refs.fg.style.left = `50%`;
      this.$refs.fg.style.transform = `translate3d(-53%, 30%, 0)`;
      this.$refs.bg.style.transform = `scale3d(1, 1, 1)`;
    },
    returnanimation() {
      this.$refs.fg.style.maxWidth = `50%`;
      this.$refs.fg.style.maxHeight = `50%`;
      this.$refs.fg.style.top = `0%`;
      this.$refs.fg.style.left = `50%`;
      this.$refs.fg.style.transform = `translate3d(-53%, 30%, 0)`;
      this.animating = false;
      this.$refs.bg.style.transform = `scale3d(0.435, 0.435, 0.435)`;
    },
  },
};
</script>

<style scoped>
.container_row {
  margin: 0;
  position: relative;
}

.layer1 {
  position: absolute;
  z-index: 1;
  left: 0;
  top: 0;
}

.layer2 {
  position: absolute;
  z-index: 2;
  left: 0;
  top: 0;
}

.bg {
  position: absolute;
  transform: scale3d(0.435, 0.435, 0.435);
  overflow: hidden;
  border-radius: 100%;
  width: 400px;
  height: 400px;
  text-align: center;
  transition: transform 0.6s cubic-bezier(1, 0.005, 0.37, 1.645);
  animation-duration: 0.75s;
  animation-fill-mode: backwards;
  animation-delay: 0.5s;
}
.fg {
  max-width: 50%;
  max-height: 50%;
  position: relative;
  top: 0%;
  left: 50%;
  transform: translate3d(-53%, 30%, 0);
  z-index: 999;
  -ms-grid-row-align: center;
  align-self: center;
  -ms-grid-column-align: center;
  justify-self: center;
  transition: transform 0.6s cubic-bezier(1, 0.005, 0.37, 1),
    top 0.6s cubic-bezier(1, 0.005, 0.37, 1);
}

.t .st {
  text-align: center;
}

@keyframes animatebg {
  0% {
    transform: scale3d(0, 0, 0);
  }
  100% {
    transform: scale3d(0.5, 0.5, 0.5);
  }
}
</style>
