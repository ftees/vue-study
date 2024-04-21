<template>
  <div class="menu-container">
    <a-menu id="dddddd" v-model:openKeys="openKeys" v-model:selectedKeys="selectedKeys"
      style="width: 256px; height: 100vh; padding-top: 20px;" mode="inline" :items="items"
      @click="handleClick"></a-menu>
  </div>
</template>
<script lang="ts" setup>
import { reactive, ref, watch, VueElement, h } from 'vue';
import { MailOutlined, AppstoreOutlined } from '@ant-design/icons-vue';
import type { MenuProps, ItemType } from 'ant-design-vue';
import { useRouter } from "vue-router";

const selectedKeys = ref<string[]>(['1']);
const openKeys = ref<string[]>(['sub1']);
const router = useRouter();

function getItem(
  label: VueElement | string,
  key: string,
  icon?: any,
  children?: ItemType[],
  type?: 'group',
): ItemType {
  return {
    key,
    icon,
    children,
    label,
    type,
  } as ItemType;
}

const items: ItemType[] = reactive([
  getItem('Home', 'home', () => h(MailOutlined)),

  getItem('About', 'about', () => h(AppstoreOutlined)),
]);

const handleClick: MenuProps['onClick'] = e => {
  console.log('click', e.key);
  router.push(`/${e.key}`)
};

watch(openKeys, val => {
  console.log('openKeys', val);
});
</script>
<style lang="css"></style>