<template>
  <div>
    <div class="flex items-center justify-center group w-screen">

        <div class="p-4 bg-gray-800 flex justify-between items-center rounded-xl my-6 md:w-1/2 w-5/6">

          <div class="flex">
            <img :class="is_completed ? 'block' : 'hidden' " 
            :src="require('@/assets/images/checked_checkbox.svg')" alt="" class="h-6 w-6">


            <div :class="is_completed ? 'hidden' : 'block'" @click="emitViewEvent(Todo)"
            title="Mark as complete"
            class="h-6 w-6 border-2 border-pink-500 bg-transparent rounded-md cursor-pointer">
              
            </div>

            <div  @click="emitViewEvent(Todo)"
            class="text-white font-semibold text-base md:text-lg mx-4">
              {{Todo.title}}
            </div>
          </div>

          <div>
            <img @click="emitDeleteEvent(Index)" 
            :src="require('@/assets/images/delete.svg') " 
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

    is_completed: {
      type: Boolean,
      default: false,
    
    },

    Todo: {
      title: String,
      default: 'New item',
      type: Object
    },

    Index: {
      type: Number
    }

  },

  data(){
    return{
    }
  },

  methods: {
    taskComplete(){
      this.is_completed = !this.is_completed
    },

    emitDeleteEvent(todo_id){
      this.$emit("deleteTodo", todo_id)
    },

    emitViewEvent(todo){
      this.$emit("viewTodo", todo)
    }
  }
}
</script>

<style>

</style>