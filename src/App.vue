<template>
  <div class="input-container">
    <s-input
      class="i18n-input"
      :class="current ? 'be-input' : 'af-input'"
      :disabled="!current"
      placeholder="plze input"
      v-model:value="enText"
    />
    <s-input
      class="i18n-input"
      :class="!current ? 'be-input' : 'af-input'"
      :disabled="current"
      placeholder="请输入"
      v-model:value="zhText"
    />
    <img
      class="tran-icon"
      src="../public/i18n-icon.svg"
      height="24"
      width="24"
      @click="handleClick"
    />
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";
import SInput from "./components/CustomInput.vue";

// enum I18nText {
//   ZH = 'zh-CN',
//   EN = 'en-US'
// }
// true means I18nText.ZH
const current = ref(true);
const zhText = ref("");
const enText = ref("");

function handleClick() {
  current.value = !current.value;
}
</script>
<style scoped lang="postcss">
.input-container {
  height: 45px;
  position: relative;

  .be-input {
    position: absolute;
    left: 0;
    bottom: 0;
    width: 135px;
    height: 14px;
    z-index: 2;
  }
  .af-input {
    position: absolute;
    left: 0;
    top: 0;
    padding: 0;
    z-index: 1;
  }
  .i18n-input {
    transition: all 0.5s linear;
  }
}
.tran-icon {
  cursor: pointer;
  position: absolute;
  left: 160px;
  bottom: 6px;
}
</style>
