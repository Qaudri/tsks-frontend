<template>
  <div>
    <div class="flex items-center group">

        <div :class="taskItem ? 'block' : 'hidden' "
        class="p-4 bg-gray-800 flex items-center justify-center rounded-xl my-6">

          <img :class="is_completed ? 'block' : 'hidden' " :src="require('@/assets/images/checked_checkbox.svg')" alt="" class="h-8 w-8">

          <div :class="is_completed ? 'hidden' : 'block'"  @click="taskComplete" title="Mark as complete"
          class="h-6 w-6 border-2 border-pink-500 bg-transparent rounded-md cursor-pointer">
            
          </div>

          <div class="text-white font-semibold text-base md:text-lg mx-4">
            Read on Nuxt Js Slot usage.
          </div>

          <div class="md:ml-36 text-white">
            10:00am
          </div>

        </div>

        <img @click="deleteItem" :class="taskItem ? 'block' : 'hidden' "
        :src="require('@/assets/images/delete.svg') " title="Delete this item" 
        class="mx-4 h-6 w-6 cursor-pointer hidden group-hover:block" />

    </div>
  </div>
</template>

<script>
export default {
  data(){
    return{
      is_completed: false,
      taskItem: true
    }
  },

  methods: {
    taskComplete(){
      this.is_completed = !this.is_completed,

      setTimeout(() => {
        this.taskItem = !this.taskItem
      }, 1000);
    },

    deleteItem(){
      this.taskItem = !this.taskItem
    }
  }
}
</script>

<style>

</style>