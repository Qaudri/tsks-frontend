<template>
  <div class="">
    <button class="">
      {{title}}
    </button>
  </div>
</template>

<script>
export default {
  props: {

    button:{
      title: String,
      default: 'Button'
    },

  }
}
</script>

<style>

</style>