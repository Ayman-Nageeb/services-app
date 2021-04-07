<template>
  <div class="item-block" style="cursor: pointer" @click="$emit('showcontactdrawer')">
    <div class="pa-4 title-block" @mouseenter="animate" @mouseleave="endanimate">
      <span class="display-1 font-weight-black">{{ name }}</span>
      <span class="mx-4"></span>
      <div style="display: inline-block; transition: 1s" ref="arrow"></div>
      <v-icon style="transition: 1s" color="red">mdi-arrow-right</v-icon>
    </div>
    <div>Help you build something</div>
  </div>
</template>

<script>
export default {
  props: ["name"],
  methods: {
    animate() {
      this.$refs.arrow.style.width = "40px";
    },
    endanimate() {
      this.$refs.arrow.style.width = "0px";
    },
  },
};
</script>

<style>
.item-block {
  border-right: 1px solid #ccc;
}
.title-block:hover {
  color: #d5333e;
  cursor: pointer;
}
</style>
