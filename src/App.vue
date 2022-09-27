<script setup lang="ts">
import ButtonTab from './ButtonTab.vue';
import ChromeTab from './ChromeTab.vue';
import { useBoolean } from './composables';

const { bool: darkMode, toggle } = useBoolean();

function handleDarkMode() {
  toggle();
}
</script>

<template>
  <div class="h-full p-24px text-14px bg-#f6f9f8" :class="{ '!bg-#101014 text-light': darkMode }">
    <div>
      <span class="pr-24px text-24px font-bold">暗黑模式</span>
      <input type="checkbox" :checked="darkMode" @change="handleDarkMode">
    </div>
    <h3 class="pb-24px text-24px font-bold">
      ButtonTab
    </h3>
    <div class="tab-shadow pl-16px py-8px bg-white" :class="{ '!bg-dark text-white': darkMode }">
      <ButtonTab :dark-mode="darkMode">
        default
      </ButtonTab>
      <ButtonTab :dark-mode="darkMode" :is-active="true" class="ml-12px">
        active
      </ButtonTab>
      <ButtonTab :dark-mode="darkMode" :closable="false" class="ml-12px">
        no-close
      </ButtonTab>
    </div>
    <div class="tab-shadow px-16px py-8px mt-12px bg-white" :class="{ '!bg-dark text-white': darkMode }">
      <ButtonTab :dark-mode="darkMode" primary-color="#5856D6">
        default
      </ButtonTab>
      <ButtonTab :dark-mode="darkMode" primary-color="#5856D6" :is-active="true" class="ml-12px">
        active
      </ButtonTab>
      <ButtonTab :dark-mode="darkMode" primary-color="#5856D6" :closable="false" class="ml-12px">
        no-close
      </ButtonTab>
    </div>
    <h3 class="py-24px text-24px font-bold">
      ChromeTab
    </h3>
    <div class="tab-shadow pl-16px py-8px bg-white" :class="{ '!bg-dark text-white': darkMode }">
      <ChromeTab :dark-mode="darkMode">
        default
      </ChromeTab>
      <ChromeTab :dark-mode="darkMode" :is-active="true">
        active
      </ChromeTab>
      <ChromeTab :dark-mode="darkMode" :closable="false">
        no-close
      </ChromeTab>
    </div>
    <div class="tab-shadow px-16px py-8px mt-12px bg-white" :class="{ '!bg-dark text-white': darkMode }">
      <ChromeTab :dark-mode="darkMode" primary-color="#5856D6">
        default
      </ChromeTab>
      <ChromeTab :dark-mode="darkMode" primary-color="#5856D6" :is-active="true">
        active
      </ChromeTab>
      <ChromeTab :dark-mode="darkMode" primary-color="#5856D6" :closable="false">
        no-close
      </ChromeTab>
    </div>
  </div>
</template>

<style>
html,
body,
#app {
  height: 100%;
}

.tab-shadow {
  box-shadow: 0 1px 2px rgb(0 21 41 / 8%);
}
</style>
