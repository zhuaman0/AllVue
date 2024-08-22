<template>
  <div>
    <q-layout view="hHr LpR lFf" container style="height: 100vh;">
      <q-header v-model="header" reveal elevated bordered>
        <q-toolbar class="bg-purple text-white">
          <q-btn flat round dense icon="assignment_ind" />
          <q-toolbar-title>
            Toolbar
          </q-toolbar-title>
          <q-btn flat round dense icon="apps" class="q-mr-xs" />
          <q-btn flat round dense icon="more_vert" />
          <!-- Menu button to toggle the drawer -->
          <q-btn @click="toggleDrawer" flat icon="menu" label=""/>
        </q-toolbar>
      </q-header>

      <q-page-container>
        <q-page>
          <router-view />
        </q-page>
      </q-page-container>

      <q-drawer
        side="left"
        v-model="drawerLeft"
        bordered
        :width="200"
        :breakpoint="500"
        content-class="bg-grey-3"
        show-if-above
      >
        <q-scroll-area style="height: 100vh; max-width: 300px;">
          <h1>Baby</h1>
        </q-scroll-area>
      </q-drawer>
    </q-layout>
  </div>
</template>
+
<script setup>
import { ref, watch } from 'vue';

// Reactive state for the drawer's visibility
const drawerLeft = ref(false);

// Method to toggle the drawer
const toggleDrawer = () => {
  drawerLeft.value = !drawerLeft.value;
};

// Watcher to observe changes in the drawer's visibility
watch(drawerLeft, (newValue) => {
  console.log('Drawer state changed:', newValue ? 'Open' : 'Closed');
});
</script>

<style>
/* Add any custom styles here */
</style>
