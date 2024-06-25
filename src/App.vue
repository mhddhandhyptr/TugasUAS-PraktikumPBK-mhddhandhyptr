<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Tugas UAS Dhandhy
        </q-toolbar-title>
        <q-btn flat round icon="menu" @click="toggleDrawer" />
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="drawer" side="left" overlay>
      <q-list>
        <q-item clickable v-ripple to="/">
          <q-item-section>
            <q-item-label>Weather</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple to="/task1">
          <q-item-section>
            <q-item-label>Daftar Tugas</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

    <q-footer class="text-center">
      <div>Muhammad Dhandhy Putera Irvantie - 223510351</div>
    </q-footer>
  </q-layout>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      drawer: false,
    };
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },
  },
};
</script>

<style>
@import 'quasar/dist/quasar.sass';

body {
  font-family: 'Quicksand', sans-serif;
}
</style>
