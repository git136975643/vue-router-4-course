
<script setup>
import sourceData from "@/data.json"
import { ref } from "vue"
const destinations = ref(sourceData.destinations)
</script>

<template>
  <nav id="nav">
    <AppLink id="logo" to="/">旅行App</AppLink>
    <AppLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{name:'destination.show',params:{id:destination.id ,slug:destination.slug}}"
    >{{destination.name}}</AppLink>
    <AppLink :to="{name:'protected'}">登录</AppLink>
    <AppLink to="https://www.baidu.com">去百度</AppLink>
  </nav>
</template>

<style  >
.router-link-active {
  border-bottom: 1px solid red;
}
</style>