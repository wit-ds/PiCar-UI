<template>
  <ButtonsChild :buttons="buttons" :cols="cols"/>
</template>

<script>
import ButtonsChild from '@/components/controll/child/ButtonsChild.vue'

export default ({
  name: 'HeadControlMod',
  components: {
    ButtonsChild
  },
  data: () => ({
    buttons: [
      [false, 'Left', 'lookleft', 74, 'LRstop'],
      [false, 'Up', 'armup', 73, 'armstop'],
      [false, 'Right', 'lookright', 76, 'LRstop'],
      [false, 'Down', 'armdown', 75, 'armstop']
    ],
    cols: 2
  })
})
</script>

<style lang="stylus" scoped>
</style>
