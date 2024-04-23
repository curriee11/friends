<template>
    <v-container class="full-height" fluid>
      <v-row no-gutters class="full-height">
      <v-col cols="12">
       <v-list class="scrollable-list">
        <v-card @click="openChat(chat)" v-for="chat in chats" :key="chat.id" two-line>
            <v-card-actions>
          <v-row no-gutters align="center">

            <!-- Avatar Column -->
            <v-col cols="2">
              <v-avatar>
                <img :src="chat.profileImage" alt="Profile image">
              </v-avatar>
            </v-col>

            <!-- Name and Message Column -->
            <v-col class="chatcontent" cols="6">
              <v-list-item-content align="left">
                <v-list-item-title>{{ chat.name }}</v-list-item-title>
                <v-list-item-subtitle>{{ chat.lastMessage }}</v-list-item-subtitle>
              </v-list-item-content>
            </v-col>

            <!-- Seen/Unseen Icon and Time -->
            <v-col cols="2">
              <v-row justify="end">
                <div class="justify-self-end">
                <v-list-item-action class="me-1">
                  <div v-if="chat.unreadCount > 0">
                    <v-badge color="#6e00ff" :content="chat.unreadCount">
                      <v-icon color="grey">mdi-message</v-icon>
                    </v-badge>
                  </div>
                  <!-- <div v-else>
                    <v-icon :color="chat.seen ? '6e00ff' : 'default'">
                      {{ chat.seen ? 'mdi-check-all' : 'mdi-check' }}
                    </v-icon>
                  </div> -->
                </v-list-item-action> 
                <!-- <v-list-item-action-text align="left" class="custom-time">{{ chat.time }}</v-list-item-action-text> -->
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
export default {
  name: "ChatList",
  data() {
    return {
      chats: [
        {
          id: 1,
          name: "Alice Freeman",
          lastMessage: "Hey, how’s it going?",
          profileImage:
            "https://static.vecteezy.com/system/resources/previews/002/275/847/original/male-avatar-profile-icon-of-smiling-caucasian-man-vector.jpg",
          time: "7:34pm",
          seen: true,
          unreadCount: 0,
        },
        {
          id: 2,
          name: "Claire Blue",
          lastMessage: "Hey, Pay me!",
          profileImage:
            "https://e7.pngegg.com/pngimages/799/987/png-clipart-computer-icons-avatar-icon-design-avatar-heroes-computer-wallpaper-thumbnail.png",
          time: "12:34pm",
          seen: false,
          unreadCount: 0,
        },
        {
          id: 3,
          name: "Daisy Ros",
          lastMessage: "Hey, what is up?",
          profileImage:
            "https://www.svgrepo.com/show/382100/female-avatar-girl-face-woman-user-7.svg",
          time: "5:34am",
          seen: false,
          unreadCount: 5,
        },
      ],
    };
  },
  methods: {
    openChat(chat) {
      // Here you can emit an event or directly call a method in the parent component
      // to update the profile icon and name in the ChatBox component
      console.log("Selected chat:", chat);
      this.$emit("update-chat-box", chat);
    },
  },
};
</script>
 
 <style scoped>
.full-height {
  height: 100vh; 
}
.scrollable-list {
  overflow-y: auto; 
  height: 100%; 
}

.v-list {
  background-color: #ffffff;
  border-radius: 0.25rem;
  margin: 0;
  padding: 0;
  overflow-y: auto;
  height: 100%;
}
.v-container, .v-row, .v-col {
  padding: 0;
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
}

/* .v-list-item {
  align-items: center; 
} */
/* .custom-time {
  color: #555; 
  font-size: 10px;
  font-weight: 600;
} */
</style>