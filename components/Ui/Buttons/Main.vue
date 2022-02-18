<template>
  <div class="">
    <button class="text-white bg-pink-700 py-3 px-6 font-semibold rounded-lg 
        mx-6">
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