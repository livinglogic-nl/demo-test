<template>
  <div class="app">
    <main>
      <creation-view v-for="creation in creations" :creation="creation" />
    </main>
    <footer>
      <h2>Replay demo creation</h2>
      <p>Please visit <a v-html="replayDemoLink" /> for a visualization of the events that created this demo.</p>
      <p>Feel free to add your own color, words and pattern to the next demo! 🚀</p>
    </footer>
  </div>
</template>
<script setup lang="ts">

import { creations } from './creations';
import CreationView from './CreationView.vue';

const replayDemoUrl = 'https://livinglogic.nl/demo';
const replayDemoLink = `<a href="${replayDemoUrl}">${replayDemoUrl}</a>`;

</script>
<style>

.app {
  main {
    margin: 50px 0;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 100px;
  }
  .creation-view {
  }
}

</style>
