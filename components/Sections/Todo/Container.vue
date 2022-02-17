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
          <SectionsTodoItem id="listItem"/>
          <SectionsTodoItem id="listItem"/>
          <SectionsTodoItem id="listItem"/>
          <SectionsTodoItem id="listItem"/>
          <SectionsTodoItem id="listItem"/>

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

  },

  methods: {
    addListItem(){
      this.clone = node.cloneNode(true);
    }
  }
}
</script>

<style>

</style>