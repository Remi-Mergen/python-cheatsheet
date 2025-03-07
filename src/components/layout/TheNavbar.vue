<script setup lang="ts">
const navigation = useNavigationStore()
const route = useRoute()
</script>

<template>
  <nav
    class="sticky top-0 z-40 w-full flex-none border-b border-slate-900/10 bg-white/90 backdrop-blur dark:border-slate-50/[0.06] dark:bg-transparent lg:z-50"
  >
    <div class="mx-auto max-w-8xl px-2 sm:px-6 lg:px-12">
      <div class="relative flex h-14 justify-between">
        <the-sidebar-mobile />

        <!-- menu -->
        <div class="ml-14 flex flex-1 items-center space-x-6 lg:ml-0">
          <div class="mr-3 flex flex-shrink-0 items-center">
            <router-link to="/">
              <img
                class="h-5 w-auto"
                src="https://raw.githubusercontent.com/wilfredinni/merken/master/static/merken/img/snake.svg"
                alt="python-cheatsheet"
                height="10"
                width="10"
              />
            </router-link>
          </div>

          <algolia-doc-search />

          <base-badge
            url="https://news.pythoncheatsheet.org/"
            class="hidden lg:flex"
          >
            <span class="hidden xl:flex">
              ✨ The first Issue of the Python Cheatsheet is out!
            </span>
            <span class="hidden lg:block xl:hidden"> ✨ Issue 1 is out! </span>
          </base-badge>
        </div>

        <!-- actions -->
        <div
          class="absolute inset-y-0 right-0 flex items-center space-x-5 pr-2 sm:static sm:inset-auto sm:ml-6 sm:pr-0"
        >
          <div
            class="hidden border-r border-slate-200 pr-6 dark:border-slate-800 sm:ml-6 sm:space-x-6 lg:flex"
          >
            <template
              v-for="item in navigation.navbarNavigation"
              :key="item.name"
            >
              <router-link
                v-if="item.internal"
                :to="item.path"
                class="inline-flex items-center px-1 pt-1 text-sm font-medium transition duration-300"
                :class="
                  route.path === item.path
                    ? 'text-sky-600 dark:text-sky-400'
                    : 'text-slate-700 hover:text-sky-500 dark:text-gray-200 dark:hover:text-sky-400'
                "
              >
                {{ item.name }}
              </router-link>

              <a
                v-else
                :href="item.path"
                target="_blank"
                class="inline-flex items-center px-1 pt-1 text-sm font-medium text-slate-700 transition duration-300 hover:text-sky-500 dark:text-gray-200 dark:hover:text-sky-400"
              >
                {{ item.name }}
              </a>
            </template>
            <a
              href="https://smartlnks.com/QhT3f"
              target="_blank"
              class="inline-flex items-center px-1 pt-1 text-sm font-medium text-slate-700 transition duration-300 hover:text-sky-500 dark:text-gray-200 dark:hover:text-sky-400"
            >
              Sponsor
              <span class="ml-1 text-red-500"> ❤</span>
            </a>
            <base-reader-mode />
          </div>

          <base-theme-toggle />
          <a
            target="_blank"
            href="https://github.com/wilfredinni/python-cheatsheet/tree/master"
          >
            <github-icon />
            <span class="sr-only">python cheatsheet repository</span>
          </a>
        </div>
      </div>
    </div>
  </nav>
</template>
