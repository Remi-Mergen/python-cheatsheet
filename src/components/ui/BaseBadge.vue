<script setup lang="ts">
defineProps<{
  url: string
}>()
</script>

<template>
  <a
    :href="url"
    class="flex w-auto items-center rounded-full bg-sky-400/10 py-1 px-3 text-xs font-medium leading-5 text-sky-600 transition duration-300 hover:bg-sky-400/20 dark:text-sky-400"
  >
    <strong class="font-semibold line-clamp-1">
      <slot></slot>
    </strong>
    <svg
      width="3"
      height="6"
      class="ml-3 overflow-visible text-sky-300 dark:text-sky-400"
      aria-hidden="true"
    >
      <path
        d="M0 0L3 3L0 6"
        fill="none"
        stroke="currentColor"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      ></path>
    </svg>
  </a>
</template>
