<template>
  <div class="flex justify-center item-center">
    <div>

      <div>

        <h1 class="font-bold text-white text-6xl text-center my-4">
          Tsks, just tasks.
        </h1>

        <p class="text-white font-normal text-lg max-w-xs text-center mx-auto my-8">
          Keep track of the daily tasks in life and get that satisfaction upon completion.
        </p>

      </div>

      <div class="max-w-max mx-auto my-16">

        <a href="/signup" class="text-white bg-pink-700 py-3 px-6 font-semibold rounded-lg 
        mx-6">
          Get Started
        </a>

        <a href="" class="text-white bg-gray-800 py-3 px-6 font-semibold rounded-lg mx-6">
          Learn More
        </a>

      </div>

      <div class="m-0 p-0">
        <img :src=" require('@/assets/images/hero-image-copy.png') " alt="" width="100%" class=" mx-auto" />
      </div>

    </div>

  </div>
</template>

<script>
export default {

}
</script>

<style>

</style>