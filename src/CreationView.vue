<template>
  <div class="creation-view">
    <div class="pattern">
      <div class="dot" v-for="b in creation.pattern" :class="{ active:b }">
      </div>
    </div>
    <h2>{{creation.words.map(upper).join(' ')}}</h2>
  </div>
</template>
<script lang="ts" setup>

defineProps<{
  creation: {
    words:string[],
    pattern: number[],
  },
}>();

const upper = (s:string) => s.substring(0,1).toUpperCase() + s.substring(1);

</script>
<style>

.creation-view {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  .pattern {
    display: grid;
    grid-template-columns: repeat(5,40px);
    gap: 3px;
  }

  .dot {
    border-radius: 4px;
    --size: 40px;
    width: var(--size);
    height: var(--size);
    &.active {
      background: white;
    }
  }
}

</style>


