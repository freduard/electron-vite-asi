<script lang="ts" setup>
import ReactiveCounter from '/@/components/ReactiveCounter.vue';
import ReactiveHash from '/@/components/ReactiveHash.vue';
import ElectronVersions from '/@/components/ElectronVersions.vue';
import { RouterView, RouterLink } from 'vue-router';

const APP_VERSION = import.meta.env.VITE_APP_VERSION;
</script>

<template>
  <router-view></router-view>

  <p>
    <!-- Example how to inject current app version to UI -->
    App version: {{ APP_VERSION }}
  </p>

  <router-link to="/">Home</router-link>
  <router-link to="/about">About</router-link>

  <fieldset>
    <legend>Test Vue Reactivity</legend>
    <reactive-counter />
  </fieldset>

  <fieldset>
    <legend>Test Node.js API</legend>
    <reactive-hash />
  </fieldset>

  <fieldset>
    <legend>Environment</legend>
    <electron-versions />
  </fieldset>

  <p>
    Edit
    <code>packages/renderer/src/App.vue</code> to test hot module replacement.
  </p>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 60px auto;
  max-width: 700px;
}

fieldset {
  margin: 2rem;
  padding: 1rem;
}
</style>
