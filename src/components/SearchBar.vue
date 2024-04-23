<template>
  <v-text-field
      class="s"
        prepend-icon="mdi-magnify"
        hide-details
        outlined
        dense
        solo-inverted
      
      ></v-text-field>
</template>
<script>
  import { defineComponent } from "vue";

  export default defineComponent({
    name: "SearchBar",
  });
</script>
<style scoped>

.s{
  top: 16px;
  width: 30%;
  height: 80%;
  position: absolute;
  left: 14.5rem; 
  align-items: center;
  align-content: center;
    z-index: 1; 
   /* color: var(--color-whitesmoke); */
  box-shadow: 0px 2px 4px rgba(12, 9, 9, 0.16);
  /* border-radius: 12px; */
  /* border: 3px solid; */
  /* right: 230px!important; */
  /* color: var(--wh); */
}
@media only screen and (max-width: 1050px) {
  .s {
    
    width: 17%; /* Adjust width for smaller screens */
 
  }
}

@media only screen and (max-width: 890px) {
  .s {
    
    width: 10%; /* Adjust width for smaller screens */
 left: 190px;
  }
}

@media only screen and (max-width: 600px) {
  .s {
    left: 100px;
    width: 10%; /* Adjust width for smaller screens */
 
  }
}
@media only screen and (max-width: 408px) {
  .s {
    left: 70px;
    width: 10%; /* Adjust width for smaller screens */
 
  }
}
</style>
