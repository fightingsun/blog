<script lang="ts" setup>
/**
 * 文章列表渲染组件
 */
</script>

<template>
  <article class="mb-16 border-b">
    <!-- 预览图 -->
    <section
      class="post-picture mb-12 max-h-max rounded"
      style="background-color: #5f6266"
    >
      <NuxtLink href="/" class="relative block">
        <img
          src="~/assets/img/post.jpg"
          class="object-cover mix-blend-overlay"
          alt="文章预览图"
        />
        <!-- 渐变色 -->
        <div
          class="absolute top-0 left-0 h-full w-full opacity-70"
          style="
            background-image: linear-gradient(
              -180deg,
              rgba(0, 0, 0, 0.1) 40%,
              #000 90%
            );
          "
        ></div>
        <!-- 标题 -->
        <div
          class="absolute top-0 left-0 flex h-full w-full flex-col justify-end p-16 pt-28 text-white"
        >
          <div class="mb-4 flex flex-row text-lg">
            <span class="mr-2 underline">前端</span>
            <span class="underline">Vue</span>
          </div>
          <h2 class="text-4xl font-semibold">
            前端组件抽象化，我认为最好的方法！
          </h2>
        </div>
      </NuxtLink>
    </section>
  </article>
</template>

<style scoped>
.post-picture {
  border-bottom: 3px solid rgba(0, 0, 0, 0);
  transition: border 0.2s ease-out;
}
.post-picture:hover {
  border-color: hsl(10, 86.5%, 43.7%);
}
.post-picture > a {
  background-color: #636363;
}
.post-picture > a:hover {
  background-color: #727272;
}
</style>
