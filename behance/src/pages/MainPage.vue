<template>
  <div class="body row" style="display: flex;justify-content: center;">
    <q-card v-for="n in 6" :key="n.id" class="my-card q-ma-xl" style="width: 400px;">
      <img src="https://cdn.quasar.dev/img/mountains.jpg">
      <q-card-section>
        <div class="text-h6">Our Changing Planet</div>
        <div class="text-subtitle2">by John Doe</div>
      </q-card-section>
      <q-card-section>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit
      </q-card-section>
    </q-card>
  </div>
</template>

<script setup>
import HeaderPage from './HeaderPage.vue';

</script>

<style>

</style>
