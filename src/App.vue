<template>
  <div class=""></div>
  <div class="w-screen bg-gray-200">
    <div class="mx-auto py-16" :style="{ width, height }">
      <div class="h-1/6 shadow-lg rounded-t-lg bg-blue-500 px-10 py-8 text-white">
        <div class="flex justify-between py-2 border-b border-blue-600 border-opacity-30">
          <div class="flex items-end">
            <div class="text-5xl tracking-wider">赵青松</div>
            <div class="text-2xl pl-2">Weedustzhao</div>
          </div>
          <div class="flex items-end">
            <div class="text-3xl">前端开发</div>
            <div class="text-3xl px-2">/</div>
            <div class="text-3xl">T8</div>
          </div>
        </div>
        <div class="flex justify-between py-2">
          <div class="flex flex-col justify-around">
            <div class="">男 / 1994.12</div>
            <div class="">重庆邮电大学 - 信息安全</div>
            <div class="">本科 - 2017年毕业</div>
          </div>
          <div class="flex flex-col justify-around items-end">
            <div><sapn class="text-sm mr-2">https://weedust.com</sapn><HomeIcon class="inline-block" /></div>
            <div><sapn class="text-sm mr-2">https://github.com/ldc4</sapn><GithubIcon class="inline-block" /></div>
            <div><sapn class="text-sm mr-2">ldc4#vip.qq.com</sapn><EmailIcon class="inline-block" /></div>
            <div><sapn class="text-sm mr-2">18665341335</sapn><PhoneIcon class="inline-block" /></div>
          </div>
        </div>
      </div>
      <div class="h-5/6 shadow-lg rounded-b-lg bg-gray-50"></div>
    </div>
  </div>
</template>

<script>
import { reactive, ref, computed } from 'vue'
import HomeIcon from './components/icons/HomeIcon.vue'
import EmailIcon from './components/icons/EmailIcon.vue'
import PhoneIcon from './components/icons/PhoneIcon.vue'
import GithubIcon from './components/icons/GithubIcon.vue'

const paperSizeMap = {
  'A4': {
    height: `${Math.SQRT2 * 1024}px`,
    width: '1024px',
  }
}

export default {
  components: {
    HomeIcon,
    EmailIcon,
    PhoneIcon,
    GithubIcon
  },
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
