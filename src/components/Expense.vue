<template>

    <v-btn variant="outlined" class="expense">
  <span  class="label"> <b>+ Add Expense</b></span>
  <span class="plus">+</span>
  <!-- <span v-else><b>+</b></span> -->
  </v-btn>

  </template>
  <script>
  import { defineComponent } from "vue";
  
  export default defineComponent({
  name: "ExpenseComponent",
  });
  </script>
  <style scoped>

/* Show only the "+" sign when the label is hidden */
.plus {
  display: none;
}
@media only screen and (max-width: 899px) {
  .plus {
    display: inline;
  }
  .label {
    display: none;
  }
  .expense{
    width: 19px!important;
    right : 365px!important;
      }
}
@media only screen and (max-width: 700px) {
  .plus {
    display: inline;
  }
  .label {
    display: none;
  }
  .expense{
    width: 19px!important;
    right : 310px!important;
      }
}
   
  
  .expense{
  top: 10px;
  /* left: 1070px; */
  position: absolute;
  right: 340px;
  width: 180px;
  height: 53px!important;
  color: blueviolet;
  text-transform: none;
  font-size: 19px;
  font-family: var(--font-radley);
  border:3px solid;
  border-radius: 13px;
  }
  
  @media only screen and (max-width: 600px) {
  .expense {
   top: 11px;
    left: 190px;
    
    /* right: 300px; */
  /* top: 5vw; Adjust positioning for smaller screens */
  /* left: 24px; Adjust positioning for smaller screens */
  height: 10vw; /* Adjust height for smaller screens */
  font-size: 4vw; /* Adjust font size for smaller screens */
  border-radius: 3vw; /* Adjust border radius for smaller screens */
  padding: 2vw 4vw; /* Adjust padding for smaller screens */
  }
  }
  
  @media only screen and (max-width: 408px) {
  .expense {
   top: 11px;
    left: 150px;
    
    /* right: 300px; */
  /* top: 5vw; Adjust positioning for smaller screens */
  /* left: 24px; Adjust positioning for smaller screens */
  height: 10vw; /* Adjust height for smaller screens */
  font-size: 4vw; /* Adjust font size for smaller screens */
  border-radius: 3vw; /* Adjust border radius for smaller screens */
  padding: 2vw 4vw; /* Adjust padding for smaller screens */
  }
  }
  
  </style>
  