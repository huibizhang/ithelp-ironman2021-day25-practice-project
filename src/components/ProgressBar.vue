<template>
  <div :class="[
    'w-80 p-5',
    'bg-gray-200',
    'rounded-lg'
  ]">
    <div :class="[
      'w-full h-2',
      'bg-green-800',
      'rounded-full'
    ]">
      <div 
        :class="[
          'w-1/3 h-full',
          'bg-green-500',
          'rounded-full'
        ]"
        :style="{
          width: percent + '%'
        }"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "ProgressBar",
  props: ["minVal","maxVal","currentVal"],
  data() {
    return {
      percent: 0,
    }
  },
  mounted() {
    this.percent = Number(this.currentVal*100/(this.maxVal-this.minVal))
  },
  watch: {
    currentVal(newVal, oldVal) {
      this.percent = Number(newVal*100/(this.maxVal-this.minVal))
    }
  }
}
</script>