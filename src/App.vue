<template>
  <div>
    <div
      v-for="(div, index) in divs.values"
      :key="index"
      :ref="divs.ref"
    />
  </div>
</template>

<script>
import { ref } from 'vue'

const values = [0, 1, 2]

export default {
  setup () {
    const divEls = ref([]),
          divs = {
            ref: el => (divEls.value = [...divEls.value, el]),
            values,
          }

    return { divs }
  }
}
</script>
