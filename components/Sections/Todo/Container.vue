<template>
  <div>
    <div class="w-full bg-gray-800 py-2 px-10 h-10 hidden">

    </div>

    <div class="flex h-screen">

      <div class="hidden bg-gray-800 w-1/6 px-4 h-full ">
        <div class="w-60 bg-transparent">
          
        </div>

      </div>

      <div class="flex items-center justify-center mx-auto">
        <div>
          <SectionsTodoItem @deleteTodo="showDeleteDialog" v-for="(todo, index) in todos" 
          :key="todo.id" :Todo="todo" :Index="index" />

          <div>
            <img :src=" require('@/assets/images/add.svg') " 
            alt="" class="w-12 h-12 mx-auto" />
          </div>
        </div>
      </div> 

    </div>

  </div>
</template>

<script>
export default {
  data(){
    return{
      todos:[
        {
          id:1,
          title: "Create full home page"
        },

        {
          id:2,
          title: "Refactor entire build"
        },

        {
          id:3,
          title: "Create login verification and authentication"
        },

        {
          id:4,
          title: "Push the codebase to Github"
        },

        {
          id:5,
          title: "Go to sleep"
        },
      ],
    }
  },

  methods: {
    showDeleteDialog(Todo){
      alert("Are you sure you want to delete " + Todo)
    }
  }
}
</script>

<style>

</style>