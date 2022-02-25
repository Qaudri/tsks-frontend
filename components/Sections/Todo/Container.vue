<template>
  <div>
    <div class="w-full bg-gray-800 py-2 px-10 h-10 hidden">

    </div>



    <DialogsSimple @closeDialog="toggle_add_new_todo_dialog" :openDialog="add_new_todo_dialog" >
      <template v-slot:title>
        <div>Add new item</div>
      </template>

      <div>        
        <form @submit.prevent="submitAddNewTodoForm">

          <div class="my-2">
            <label class="font-semibold">Todo Title</label>
            <input v-model="form.todo_title" type="text" name="" id="" 
            class="my-4 w-full border-1 py-4 px-6 break-words border-gray-800 rounded-md">
          </div>

          <div class="my-2 ">
            <label for="" class="font-semibold">Todo Content</label>
            <input v-model="form.todo_content" type="text" name="" id="" 
            class="my-4 w-full h-24 border-1 py-4 px-6 break-words border-gray-800 rounded-md focus:border-pink-500 focus:border-2">
          </div>

          <div class="flex justify-center mt-10">
            <button class="px-6 py-3 rounded-lg bg-pink-500 text-white font-semibold text-base">
              Add New Item
            </button>
          </div>

        </form>
      </div>
    </DialogsSimple> 





    <DialogsSimple @closeDialog="toggleTodoDetailsDialog" :openDialog="todo_details_dialog" >
      <template v-slot:title>
        <div v-if="selected_todo">{{selected_todo.title}}</div>
      </template>

      <div v-if="selected_todo">{{selected_todo.content}}
        
      </div>

      <div class="flex justify-center mt-10">
        <button @click="taskComplete"
         class="px-6 py-3 rounded-lg bg-pink-500 text-white font-semibold text-base">
          Mark as complete
        </button>
      </div>

    </DialogsSimple> 


    <div class="flex h-screen">

      <div class="hidden bg-gray-800 w-1/6 px-4 h-full ">
        <div class="w-60 bg-transparent">
          
        </div>

      </div>

      <div class="flex items-center justify-center mx-auto">
        <div>
          <SectionsTodoItem @viewTodo="showTodoDetailsDialog" @deleteTodo="showDeleteDialog" v-for="(todo, index) in todos" 
          :key="todo.id" :Todo="todo" :Index="index" />

          <div>
            <img @click="toggle_add_new_todo_dialog" :src=" require('@/assets/images/add.svg') " 
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

      form: {
        todo_title: '',
        todo_content: ''
      },

      selected_todo: '',
      todo_details_dialog: false,
      add_new_todo_dialog: false,


      todos: [
        {
          id:1,
          title: "Create the full home page",
          content: "Using Nuxt Js, create a full home page code for tsks website. Use the dribbble work as inspo."
        },

        {
          id:2,
          title: "Refactor entire build",
          content: "Check the entire code base for errors and refactor it all. All errors must be fixed before pushing to the repo "
        },

        {
          id:3,
          title: "Create login verification and authentication",
          content: "Create a login page and a verfication process for the user. Make sure the process is thorough and clean."
        },

        {
          id:4,
          title: "Push the codebase to Github",
          content: "Once the codebase is done, push the entire system to the repository"
        },

        {
          id:5,
          title: "Go to sleep",
          content: "Get some rest and go to sleep at 11:00pm"
        },
      ],
    } 
  },

  methods: {
    showDeleteDialog(Todo){

      this.todos.splice(Todo, 1)
      console.log("Item deleted successfully")

    },

    toggleTodoDetailsDialog(){
      this.todo_details_dialog = !this.todo_details_dialog
    },

    toggle_add_new_todo_dialog(){
      this.add_new_todo_dialog = !this.add_new_todo_dialog
    },

    showTodoDetailsDialog(Todo){
      this.selected_todo = Todo;
      this.toggleTodoDetailsDialog()
    },

    taskComplete(){
      this.toggleTodoDetailsDialog();
      this.is_completed = true
    },

    submitAddNewTodoForm(){
      let todo_id = Math.floor(Math.random() * 100);

      let todo_data = {
        id: todo_id,
        title: this.form.todo_title,
        content: this.form.todo_content
      }

      this.todos.push(todo_data),
      this.toggle_add_new_todo_dialog(),
      this.form.todo_title = '',
      this.form.todo_content = ''
      
    }
  }
}
</script>

<style>

</style>