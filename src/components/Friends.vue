<!-- <template>
    <v-container fluid >
    <v-row
      class="mb-6"
      no-gutters
    >
      <v-col :cols="cols[0]">
        <v-sheet class="pa-2 ma-2">
          <ContactList/>
        </v-sheet>
      </v-col>
      <v-divider class="border-opacity-0" vertical></v-divider>
      <v-col :cols="cols[1]" class="flex-grow">
        
          <ChatBox/>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

import { defineComponent } from "vue";
// import ChatList from "./ChatList.vue"
// import ChatBox from "./ChatBox.vue";
import ContactList from "./ContactList.vue";

export default defineComponent({
  name: "FriendsComp",
  components: {ContactList,
    // ChatBox
  },
  computed: {
      cols() {
        const { lg, sm } = this.$vuetify.display
        return lg ? [3, 9] : sm ? [9, 3] : [6, 6]
      },
    },
});
</script>
<style>


</style> -->