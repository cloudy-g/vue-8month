<template>
  <tab-bar>
    <template #home>
      <tab-bar-item
        v-for="(item, index) in preference"
        :key="item.title"
        :link="item.path"
        :index="index"
        :activeColor="activeStyle"
      >
        <template v-slot:bar-icon>
          <img src="~@/assets/imgs/logo.png" alt />
        </template>
        <template v-slot:bar-icon-active>
          <img src="~@/assets/imgs/bilibilil.png" alt />
        </template>
        <template v-slot:bar-title="{actives}">
          <div :style="actives">{{item.title}}</div>
        </template>
      </tab-bar-item>
    </template>
  </tab-bar>
</template>

<script>
import TabBar from "@/components/TabBar/TabBar";
import TabBarItem from "@/components/TabBar/TabBarItem";

export default {
  name: "MainBar",
  data() {
      return {
          activeStyle: "#f40",
      }
  },
  props:{
      preference: Array
  },
  computed: {
      
  },
  components: {
    TabBar,
    TabBarItem,
  },
};
</script>

<style>
</style>