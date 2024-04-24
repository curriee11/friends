<template>
  <v-app>
    
    <v-app-bar :elevation="0"  style="height: 74px; background-color:var(--color-whitesmoke); ">
     <NavBar/>
    </v-app-bar>
      
     <!-- <MenuBar1 /> -->
     <Sidebar />
     <v-main style="background-color: #F8F2FF; " >
  <!-- <FriendsComp/> -->
  <FriendsMain/>

    </v-main>

  </v-app>

</template>
<script>
  import { defineComponent } from "vue";

  import Sidebar from "../components/Sidebar.vue";
  import NavBar from "../components/NavBar.vue";
//  import ChatList from '../components/ChatList.vue'
// import FriendsComp from "../components/Friends.vue"
import FriendsMain from "../components/FriendsMain.vue" ; 

  export default defineComponent({
    name: "MaskGroup",
    components: { NavBar,  Sidebar, FriendsMain
      // FriendsComp
    },
  });
</script>
<style module>

/* .friends{
  display: flex;
}
.chatListWrapper {
  width: 70%;
}
 /* Override the default height of v-app-bar */
  

  /* .notificationIcon {
    position: absolute;
    top: 23px;
    left: 1103px;
    width: 50px;
    height: 50px;
  } */
   /* .notificationIcon:active  {
    color: aqua!important;;
  }
  
  .dashboard {
    position: absolute;
    top: -59px;
    left: 0px;
    border-radius: 30px;
    background-color: var(--color-whitesmoke);
    width: 1777px;
    height: 920px;
    overflow: hidden;
  }
  .maskGroup {
    width: 100%;
    position: relative;
    height: 830px;
  }
  .icon{
    color: #673ab7;
  } */ 
  
</style>