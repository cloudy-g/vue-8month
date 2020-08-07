<template>
  <div @click="btnClick" class="tab-bar-item">
    <slot v-if="isActive" name="bar-icon"></slot>
    <slot v-else name="bar-icon-active"></slot>
    <slot :actives="activeColors" name="bar-title"></slot>
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  data() {
      return {
        
      }
  },
  props: {
    link: String,
    index: Number,
    activeColor: String
  },
  computed: {
      activeColors() {
          return this.isActive ? {} : {color: this.activeColor}
      },
      isActive() {
          return this.$route.path !== this.link
      }
  },
  methods: {
    btnClick() {
      this.$router.push(this.link);
      let tabs = [...document.getElementsByClassName("tab-bar-item")];
      tabs.forEach((el) => {
        el.children[0].className = "simple";
        el.children[1].className = "hidden";
      });
      let target = tabs[this.index];
      target.children[0].className = "hidden";
      target.children[1].className = "simple";
    },
  },
};
</script>

<style lang="less">
.tab-bar-item {
  flex: 1;
  text-align: center;
  img {
    margin-top: 5px;
    height: 20px;
    width: 20px;
    vertical-align: middle;
  }
}
</style>