<template>
  <header class="flex min-h-fit flex-row items-center justify-between p-16">
    <div>
      <button v-show="false">
        <Icon
          name="material-symbols:home-outline-rounded"
          class="opacity-70"
          style="color: #4b4f55"
          size="30px"
        />
      </button>
    </div>
    <div>
      <button class="pl-6 opacity-70">
        <Icon
          name="material-symbols:search-rounded"
          style="color: #4b4f55"
          size="30px"
        />
      </button>
      <button class="pl-6 opacity-70">
        <Icon
          name="material-symbols:menu-rounded"
          style="color: #4b4f55"
          size="30px"
        />
      </button>
    </div>
  </header>
  <div
    class="mx-auto flex w-4/5 max-w-screen-xl flex-row justify-between pt-10 pb-32"
  >
    <!-- 侧边栏 -->
    <aside class="basis-3/12">
      <!-- logo 和 网站描述 -->
      <section class="border-b pb-12">
        <!-- logo -->
        <div class="mb-8">
          <a href="/">
            <img src="~/assets/img/logo.jpg" alt="Logo" />
          </a>
        </div>
        <!-- 博客介绍 -->
        <p class="text-lg tracking-widest" style="color: #5f6266">
          欢迎来到我的博客，我会将我在工作、学习中的一些编程经验和技巧已经踩过的坑都记录在这，欢迎指正！
        </p>
      </section>
      <!-- 搜索框 -->
      <section class="border-b py-12">
        <div class="cursor-text rounded-sm border p-4">
          <Icon
            name="material-symbols:search-rounded"
            style="color: #d3d7db"
            class="mr-3"
            size="24px"
          />
          <span class="text-sm tracking-widest" style="color: #535763"
            >搜索</span
          >
        </div>
      </section>
    </aside>
    <!-- 内容 -->
    <section class="basis-8/12">
      <NuxtPage />
    </section>
  </div>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 0.4s;
}
.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(1rem);
}
button:hover {
  opacity: 1;
}
</style>
