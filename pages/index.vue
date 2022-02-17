<template>
  <div>

    <div class="h-screen sticky">

      <div>
        <SectionsCommonHeader />
      </div>

      <div>
        <SectionsHero />
      </div>

    </div>
 
    <!-- <div>
      <SectionsTodoContainer />
    </div> -->

  </div>
</template>

<script>

</script>

<style>
body{
  background: #111111;
  padding: 0;
  margin: 0;
}

.sticky{
  position: -webkit-sticky;
  position: sticky;
  top:0;
  z-index: 0;
  max-height: 100vh;
}
</style>
