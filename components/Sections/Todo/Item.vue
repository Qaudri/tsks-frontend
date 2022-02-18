<template>
  <div>
    <div class="flex items-center justify-center group w-screen">

        <div class="p-4 bg-gray-800 flex justify-between items-center rounded-xl my-6 md:w-1/2 w-5/6">

          <div class="flex">
            <img :class="is_completed ? 'block' : 'hidden' " @click="taskComplete"
            :src="require('@/assets/images/checked_checkbox.svg')" alt="" class="h-6 w-6">


            <div :class="is_completed ? 'hidden' : 'block'"  @click="taskComplete" 
            title="Mark as complete"
            class="h-6 w-6 border-2 border-pink-500 bg-transparent rounded-md cursor-pointer">
              
            </div>

            <div  :class="is_completed ? 'opacity-30' : 'opacity-100' " 
            class="text-white font-semibold text-base md:text-lg mx-4">
              {{Todo.title}}
            </div>
          </div>

          <div>
            <img @click="emitDeleteEvent(Todo.id)" :class="taskItem ? 'block' : 'hidden' "
            :src="require('@/assets/images/delete.svg') " title="Delete this item" 
            class="mx-4 h-6 w-6 cursor-pointer items-end" />
          </div>

          <!-- <div class="text-white">
            10:00am
          </div> -->

        </div>



    </div>
  </div>
</template>

<script>
export default {

  props: {

    Todo: {
      title: String,
      default: 'New item',
      type: Object
    }

  },

  data(){
    return{
      is_completed: false,
      taskItem: true
    }
  },

  methods: {
    taskComplete(){
      this.is_completed = !this.is_completed
    },

    emitDeleteEvent(todo_id){
      this.$emit("deleteTodo", todo_id)
    }
  }
}
</script>

<style>

</style>