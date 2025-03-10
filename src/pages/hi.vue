<!--
 * @Author: weisheng
 * @Date: 2024-11-01 11:44:38
 * @LastEditTime: 2024-11-14 19:02:48
 * @LastEditors: weisheng
 * @Description:
 * @FilePath: \wot-demo\src\pages\hi.vue
 * 记得注释
-->
<script lang="ts" setup>
const columns = ref(['选项1', '选项2', '选项3', '选项4', '选项5', '选项6', '选项7'])
const value = ref('')

function handleConfirm(option: { value: string }) {
  value.value = option.value
}

function handleClick() {
  value.value = ''
  columns.value = []
}

function handleRemove() {
  value.value = ''
  columns.value = ['选项1', '选项2']
}

function handleReset() {
  columns.value = ['选项1', '选项2', '选项3', '选项4', '选项5', '选项6', '选项7']
  value.value = ''
}
</script>

<template>
  <view class="px-3 py-20 text-center">
    <wd-picker v-model="value" custom-class="mb-5" :columns="columns" label="单列选项" @confirm="handleConfirm"/>
    <wd-button type="primary" @click="handleClick">变更选项为空[]</wd-button>
    <wd-button type="primary" @click="handleRemove">减少选项</wd-button>
    <wd-button type="info" @click="handleReset">重置默认</wd-button>
  </view>
  <text>
    {{ columns }}
  </text>
</template>

<route lang="json">
{
"layout": "tabbar",
"name": "hi",
"style": {
"navigationBarTitleText": "hi"
}
}
</route>
