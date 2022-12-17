<script lang="ts" setup>
/**
 * 文章列表渲染组件
 */

const pageData = reactive({
  pageCount: 3,
  page: 1,
  pageSize: 5,
});
</script>

<template>
  <div>
    <article v-for="item in pageData.pageSize" class="mb-16 border-b">
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
      <!-- 作者，发布日期，阅读时长 -->
      <section class="mb-12">
        <div class="flex">
          <!-- 作者 -->
          <NuxtLink href="/" class="mr-12 flex items-center">
            <img
              src="~/assets/img/logo.jpg"
              class="mr-4 h-9 w-9 rounded-full"
              alt=""
            />
            <span class="font-medium tracking-widest" style="color: #1a1b1cb3"
              >Elvin Sun</span
            >
          </NuxtLink>
          <NuxtLink href="/" class="mr-12 flex items-center">
            <Icon
              name="material-symbols:date-range-outline"
              size="20px"
              style="color: #d02f0f"
              class="mr-4"
            />
            <span class="font-medium tracking-widest" style="color: #4b4f55cc"
              >2022/12/16</span
            >
          </NuxtLink>
          <NuxtLink href="/" class="flex items-center">
            <Icon
              name="material-symbols:nest-clock-farsight-analog-outline"
              size="20px"
              style="color: #d02f0f"
              class="mr-4"
            />
            <span class="font-medium tracking-widest" style="color: #4b4f55cc"
              >6分钟读完</span
            >
          </NuxtLink>
        </div>
      </section>
      <!-- 文章摘要 -->
      <section class="mb-12">
        <p class="text-base tracking-widest" style="color: #5f6266">
          基于2大主流前端框架下，前端的主要的工作其实就是在编写各种组件。似乎所有人都在说前端开发的天花板很低，除了一些特别的方向，很少有人在前端功能的开发上遇到过什么难题。这也导致没有人关注和讨论前端组件的抽象，大家都忙于做功能的开发。甚至有些前端开发在完全不做抽象的情况下仅用少数几个组件就完成了对整个SPA的开发。
        </p>
      </section>
      <NuxtLink
        href="/"
        class="mb-16 block w-1/5 border py-3 text-center tracking-widest hover:border-gray-400"
        style="color: #5f6266; font-size: 13px"
        >阅读</NuxtLink
      >
    </article>
    <!-- 分页 -->
    <div class="flex items-center justify-between">
      <!-- 上一页按钮 -->
      <div
        v-if="pageData.page === 1"
        class="w-1/5 cursor-default border py-3 text-center tracking-widest opacity-30"
      >
        <Icon
          name="material-symbols:arrow-back"
          size="18px"
          style="color: #919395"
          class="mr-2"
        />
        <span style="color: #4b4f55; font-size: 13px">上一页</span>
      </div>
      <NuxtLink
        v-else
        href="/"
        class="page-btn w-1/5 py-3 text-center tracking-widest"
        style="font-size: 13px"
      >
        <Icon name="material-symbols:arrow-back" size="18px" class="mr-2" />
        <span class="align-middle" style="font-size: 13px">上一页</span>
      </NuxtLink>
      <!-- 页码 -->
      <span style="color: #5f6266; font-size: 0.85rem"
        >{{ pageData.page }} / {{ pageData.pageCount }}</span
      >
      <!-- 下一页按钮 -->
      <div
        v-if="pageData.page === pageData.pageCount"
        class="w-1/5 cursor-default border py-3 text-center tracking-widest opacity-30"
      >
        <Icon
          name="material-symbols:arrow-forward"
          size="18px"
          style="color: #919395"
          class="mr-2"
        />
        <span style="color: #4b4f55; font-size: 13px">下一页</span>
      </div>
      <NuxtLink
        v-else
        href="/"
        class="page-btn w-1/5 py-3 text-center tracking-widest"
        style="font-size: 13px"
      >
        <Icon name="material-symbols:arrow-forward" size="18px" class="mr-2" />
        <span class="align-middle" style="font-size: 13px">下一页</span>
      </NuxtLink>
    </div>
  </div>
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
.page-btn {
  background-color: #f4f6f8;
  color: #4b4f55;
}
.page-btn:hover {
  background-color: hsl(10, 86.5%, 43.7%);
  color: white;
}
.page-btn svg {
  color: #919395;
}
.page-btn:hover svg {
  color: white;
}
</style>
