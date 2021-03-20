<template>
  <div>
    <Study />
    <Hobby />
  </div>
 
</template>

<script>
import Study from "~/components/Study"
import Hobby from "~/components/Hobby"
  export default {
   components: {
     Study,
     Hobby
   }
  }
</script>
<style>

.v-card--reveal {
  bottom: 0;
  opacity: 1 !important;
  position: absolute;
  width: 100%;
}
#card1 {
    position: relative;
    z-index: 1
}
</style>