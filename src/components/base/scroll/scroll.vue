<template>
  <div ref="rootRef">
    <slot></slot>
  </div>
</template>

<script>
import useSlider from './use-scroll'
import { ref } from 'vue'
export default {
  name: 'scroll',
  props: {
    click: {
      type: Boolean,
      default: true
    }
  },
  setup(props) {
    const rootRef = ref(null)
    useSlider(rootRef, props)

    return {
      rootRef
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus"></style>
