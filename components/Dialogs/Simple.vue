<template>
  <div v-show="openDialog" class=" absolute bg-gray-800 bg-opacity-80 flex items-center justify-center h-screen w-full">

    <div class="bg-white rounded-xl p-6 w-1/2">

      <div>
        <div class="border-b text-xl pb-4 font-semibold flex justify-between">
          <slot name="title" />

          <button>
            <img :src="require('@/assets/images/delete.svg')" alt="">
          </button>
        </div>

        <div class="my-4">
          <slot />
        </div>
        
        <div class="flex justify-center mt-8">
          <button @click="emitCloseEvent" class="px-6 py-3 rounded-lg bg-pink-500 text-white font-semibold text-base">
            {{button_title}}
          </button>
        </div>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  props: {
    openDialog: Boolean,

    button_title: {
      type: String,
      default: "Button"
    }

  },

  methods: {
    emitCloseEvent(){
      this.$emit('closeDialog')
    }
  }
}
</script>

<style>

</style>