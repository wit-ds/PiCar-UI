<template>
  <ButtonsChild :buttons="buttons" :cols="cols"/>
</template>

<script>
import ButtonsChild from '@/components/controll/child/ButtonsChild.vue'

export default ({
  name: 'ArmControlMod',
  components: {
    ButtonsChild
  },
  data: () => ({
    buttons: [
      [false, 'Grab', 'grab', 85, 'stop'],
      [false, 'Up', 'armup', 73, 'armstop'],
      [false, 'Loose', 'loose', 79, 'stop'],
      [false, 'HandUp', 'handup', 80, 'HAstop'],
      [false, 'Left', 'lookleft', 74, 'LRstop'],
      [false, 'Down', 'armdown', 75, 'armstop'],
      [false, 'Right', 'lookright', 76, 'LRstop'],
      [false, 'HandDown', 'handdown', 186, 'HAstop']
    ],
    cols: 4
  })
})
</script>

<style lang="stylus" scoped>
</style>
