<template>
  <div :class="[
      'w-screen h-screen',
      'flex flex-col',
      'justify-center items-center',
      'gap-5',
  ]">
    <input type="range" v-model="val" :min="min" :max="max" />
    <ProgressBar :currentVal="val" :minVal="min" :maxVal="max" />
  </div>
</template>

<script>
import ProgressBar from './components/ProgressBar.vue'

export default {
  data() {
    return {
      min: 0,
      max: 200,
      val: 100,
    }
  },
  components: {
    ProgressBar,
  }
}
</script>