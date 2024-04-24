<template>
      <v-container class="full-height" fluid>
      <v-row no-gutters class="full-height">
      <v-col cols="12">
       <v-list class="scrollable-list">
      <v-card
        @click="openChat(chat)"
        v-for="chat in chats"
        :key="chat.id"
        :class="{ 'selected-chat': chat.c_id === selectedChatId  }"
        two-line
      >
        <v-card-actions>
          <v-row no-gutters align="center">
            <!-- Avatar Column -->
            <v-col cols="2">
              <v-avatar>
                <img :src="chat.friend_photo" alt="Profile image" />
              </v-avatar>
            </v-col>

            <!-- Name and Message Column -->
            <v-col class="chatcontent" cols="6">
              <v-list-item-content align="left">
                <v-list-item-title class="friendName">{{ chat.friend_name }}</v-list-item-title>
                <v-list-item-subtitle class="lastMessage">{{
                  chat.last_message
                }}</v-list-item-subtitle>
              </v-list-item-content>
            </v-col>

            <!-- Seen/Unseen Icon and Time -->
            <v-col cols="2">
              <v-row justify="end">
                <div class="justify-self-end">
                  <v-list-item-action class="me-1">
                    <div v-if="chat.unread_message_count > 0">
                      <v-badge
                        color="#6e00ff"
                        :content="chat.unread_message_count"
                      >
                        <v-icon color="grey">mdi-message</v-icon>
                      </v-badge>
                    </div>
                    <!--<div v-else>
                     <v-icon :color="chat.seen ? '6e00ff' : 'default'">
                      {{ chat.seen ? 'mdi-check-all' : 'mdi-check' }}
                    </v-icon> 
                  </div>-->
                  </v-list-item-action>
                  <!-- <v-list-item-action-text class="custom-time">{{ chat.time }}</v-list-item-action-text> -->
                </div>
              </v-row>
            </v-col>
          </v-row>
        </v-card-actions>
      </v-card>
    </v-list>
    </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "ChatList",
  data() {
    return {
      chats: [],
      selectedChatId: null, 
    };
  },
  methods: {
    openChat(chat) {
      // Here you can emit an event or directly call a method in the parent component
      // to update the profile icon and name in the ChatBox component
      // console.log("Selected chat:", chat);

        console.log("chat.id ",this.selectedChatId);
        console.log("chat.id ", chat.c_id);
      this.selectedChatId = chat.c_id; 
      this.$emit("update-chat-box", chat);
    },
    // chatSelected(chat) {
    //   // Check if the chat's ID matches the ID of the selected chat
    //   return chat.c_id === this.selectedChatId;
    // },
    async getAllConversationsData() {
      await axios
        .get(`http://localhost:3000/api/friends/getMyAllConversations/2`)
        .then((response) => {
          // console.log(response.data);
          this.chats = response.data;
        })
        .catch((error) => {
          console.error("Error fetching user groups:", error);
        });
    },
  },
  mounted() {
    this.getAllConversationsData();
  },
};
</script>

<style scoped>

.full-height {
  height: 70vh; 
}
.scrollable-list {
  overflow-y: auto; 
  height: 100%; 
  /* position: absolute; */
    /* top: 159px; */
    /* left: 69px; */
    background-color: var(--color-white);
    box-shadow: 0px 4px 5px 2px rgba(241, 202, 243, 0.38);
   
 
}
.friendName{
  font-family: var(--font-roboto);
   font-weight: 600;
}
.lastMessage{
  letter-spacing: 0.05em;
    font-weight: 300;
    font-size: var(--font-size-base);
}
.selected-chat {
    background-color: #EAEAEA!important; /* Light grey background for selected chat */
  }

.v-list {
  background-color: #ffffff;
  border-radius: 0.24rem;
  margin: 0;
  padding: 0;
  overflow-y: auto;
  height: 100%;
  top:49px;
  height: 668px;
}
.v-container, .v-row, .v-col {
  padding: 4px;
  margin: 0;
}
.chatcontent{
  margin-left: 1.25rem;
  max-width: 90%;
  white-space: nowrap;
  overflow: hidden;
   
}
/* .v-list-item {
  margin-bottom: 8px;
} */
.v-avatar img {
  border-radius: 50%; 
  width: 40px; 
  height: 40px; 
}
/* .v-list-item-action-text {
  margin-right: 10px;
} */
.v-card {
  background-color: #ffffff;
  padding-top: 8px;
  border-bottom: 1px solid #b4abab;
  border-radius: 0px;
  box-shadow: none;
  border: none; 
}



</style>
