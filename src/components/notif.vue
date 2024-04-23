<template>

    <v-btn :class="notificationIcon" icon size="47" style="border: 3px solid blueviolet; position: absolute; top: 15px;">
     <v-icon class="icon">mdi-bell-outline</v-icon>
    </v-btn>
   
    </template>
    <script>
    import { defineComponent } from "vue";
    
    export default defineComponent({
    name: "notificationComponent",
    data() {
     return {
       notificationIcon: "notificationIcon",
     };
    }
    });
    </script>
    <style scoped>
    
    .notificationIcon {
    /* position: absolute; */
    top: 23px;
    /* left: 1103px; */
    right: 260px;
    width: 50px;
    height: 50px;
    }
    
    .notificationIcon:active {
    color: blueviolet;
    }
    
    
    .icon {
    color:blueviolet;
    }
    /* @media only screen and (max-width: 1600px) {
    .notificationIcon {
    
    top: 23px;
    left:1390px!important;
    width: 50px;
    height: 50px;
    }
    .user{
    left:860px;
    }
    } */
    @media only screen and (max-width: 650px) {
    .notificationIcon {
    /* position: relative; */
    top: 23px;
    right: 240px;
    /* left: 2px!important; */
    /* width: 20px!important; */
    /* height: 20px!important; */
    }
   
    }
    @media only screen and (max-width: 600px) {
    .notificationIcon {
    /* position: relative; */
    top: 23px;
    left: 290px!important;
    /* width: 20px!important; */
    /* height: 20px!important; */
    }
   
    }
    
    @media only screen and (max-width: 408px) {
    .notificationIcon {
    /* position: relative; */
    top: 23px;
    left: 230px!important;
    /* width: 20px!important; */
    /* height: 20px!important; */
    }
   
    }
    </style>
    