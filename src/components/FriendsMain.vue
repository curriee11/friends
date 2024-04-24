<template>
  <v-container fluid>
    <v-row no-gutters>
      <v-col :cols="showLeftPanel ? 4 : 0" v-if="showLeftPanel">
        <div class="left-panel">
          <v-card flat>
            <v-toolbar class="tool" color="#F8F2FF" dense flat>
            <v-row class="fill-height" no-gutters align="center">
              <v-col cols="5" class="px-0">
                <v-text-field
                  hide-details
                  dense
                  variant="solo"
                  color="transparent"
                  placeholder="Search"
                  rounded
                  clearable
                  append-inner-icon="mdi-magnify"
                  
                ></v-text-field>
              </v-col>
              <v-col cols="5">
                <v-btn variant="outlined" class="addfriend" style="border: 3px solid blueviolet; ">
                  <span class="label"  style="color: blueviolet;"><b>+ Add Friend</b></span>
                </v-btn>
              </v-col>
              <v-col cols="2">
                <v-btn class="notificationIcon" icon >
                  <v-icon class="icon">mdi-bell-outline</v-icon>
                </v-btn>
              </v-col>
            </v-row>
          </v-toolbar>
      </v-card>
          <ContactList @update-chat-box="updateSelectedChat"/>
        </div>
      </v-col>

      <v-col :cols="showLeftPanel ? 8 : 12">
        <div class="right-panel">
          <ChatBox :selectedChat="selectedChat"/>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ContactList from './ContactList.vue';
import ChatBox from './ChatBox.vue';
export default {
  name: "FriendsMain",
  components: {
    ContactList,
    ChatBox
  },
  data: () => ({
    showLeftPanel: true, // Initially show 
    selectedChat: null // Initialize selectedChat
  }),
  mounted() {
    this.handleResize();
    window.addEventListener('resize', this.handleResize);
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.handleResize);
  },
  methods: {
    handleResize() {
      const smBreakpoint = 960; //width for 'sm' in Vuetify
      this.showLeftPanel = window.innerWidth >= smBreakpoint;
    },
    updateSelectedChat(chat) {
      console.log('Selected chat:', chat.friend_photo);
      this.selectedChat = chat; // Update selectedChat when a contact is clicked
    }
  },
}
</script>

<style scoped>
/* .search-field .v-text-field.mdi-magnify:hover {
    cursor: pointer;
} */
.left-panel, .right-panel {
  padding: 16px;
}
.left-panel{
  background-color: transparent;
}
.tool{  
  box-shadow: none;
  border:0px;
}
.v-container{
  margin-top: 1rem;
  position: relative; /* Set position to relative */
  top:-59px;
}
.v-text-field{
  margin-left: 0.75rem;
  width:90%;
  box-shadow: none;
}
.v-card{
  background-color: rgba(208, 195, 210, 0.848) ;
  box-shadow: none;
}
addfriend{
  width: 80%;
  margin-left: 0.5rem;
  border-radius: 0.5rem;
  font-family: var(--font-radley);
  text-transform: capitalize; 
  color: blueviolet;
  max-width: 100%;
  white-space: nowrap;
  overflow: hidden;
}
.label{
  text-overflow: clip;
  font-size:medium;
}
.icon {
    color:blueviolet;
    }
    .notificationIcon:active {
    color: #673ab7;
    }
</style>
