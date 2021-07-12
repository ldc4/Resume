<template>
  <div class="w-screen">
    <div class="mx-auto my-8" :style="{ width, height }">
      <div class="h-1/4 bg-green-500"></div>
      <div class="h-3/4 bg-gray-100"></div>
    </div>
  </div>
</template>

<script>
import { reactive, ref, computed } from 'vue'

const paperSizeMap = {
  'A4': {
    height: `${Math.SQRT2 * 80}vw`,
    width: '80vw',
  }
}

export default {
  setup() {

    const type = ref('A4');

    const width = computed(() => {
      return paperSizeMap[type.value].width;
    });
    const height = computed(() => {
      return paperSizeMap[type.value].height;
    })

    return reactive({
      width,
      height
    })
  }
}
</script>

<style>

</style>
