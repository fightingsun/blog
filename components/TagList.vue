<script lang="ts" setup>
const tagList = reactive([
  {
    label: "前端",
    link: "http://www.baidu.com",
  },
  {
    label: "Vue",
    link: "http://www.baidu.com",
  },
  {
    label: "思维导图",
    link: "http://www.baidu.com",
  },
  {
    label: "读书",
    link: "http://www.baidu.com",
  },
  {
    label: "NodeJs",
    link: "http://www.baidu.com",
  },
  {
    label: "视频剪辑",
    link: "http://www.baidu.com",
  },
  {
    label: "Python",
    link: "http://www.baidu.com",
  },
  {
    label: "养生",
    link: "http://www.baidu.com",
  },
]);
</script>

<template>
  <div class="flex flex-wrap">
    <NuxtLink
      v-for="item in tagList"
      :key="item.label"
      :href="item.link"
      class="tag-link"
    >
      {{ item.label }}
    </NuxtLink>
  </div>
</template>

<style scoped>
.tag-link {
  margin-right: 1rem;
  margin-bottom: 1rem;
  padding: 1rem 1.8rem;
  background-color: #f4f6f8;
  color: #4b4f55;
  font-size: 12px;
  border-radius: 3px;
  transition: all 200ms ease-out;
}
.tag-link:hover {
  background-color: #d02f0f;
  color: #fff;
}
</style>
