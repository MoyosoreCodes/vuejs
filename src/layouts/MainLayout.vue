<template>
  <q-layout view="lHh LpR lFf">
    <AppHeader @toggle-sidebar="toggleSidebar"/>

    <q-drawer show-if-above v-model="showLeftSidebar" side="left">
      <AppSidebar />
    </q-drawer>

    <!-- <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
    </q-drawer> -->

    <q-page-container class="page-container">
      <q-page padding>
        <router-view />
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import AppHeader from 'src/components/AppHeader/AppHeader.vue';
import AppSidebar from 'src/components/AppSidebar/AppSidebar.vue';
import { ref } from 'vue';

const showLeftSidebar = ref(true)

function toggleSidebar() {
  showLeftSidebar.value = !showLeftSidebar.value
}
</script>

<style scoped lang="scss">
@import url('./MainLayout.scss');
</style>