<template>
  <v-app id="chat">
    <v-app-bar app clipped-right flat height="72">
      <v-responsive>
        <router-link to="/">Home</router-link> |
        <router-link to="/chat">Chat</router-link>
      </v-responsive>
      <v-spacer></v-spacer>

      <v-responsive max-width="156">
        <v-text-field
          dense
          flat
          hide-details
          rounded
          solo-inverted
        ></v-text-field>
      </v-responsive>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app width="300">
      <v-list class="pl-14" shaped>
        <v-list-item v-for="n in 5" :key="n" link>
          <v-list-item-content>
            <v-list-item-title>Room {{ n }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-navigation-drawer app clipped right>
      <v-list>
        <v-list-item v-for="n in 5" :key="n" link>
          <v-list-item-content>
            <v-list-item-title>User {{ n }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <chat-window :messages="messages" />
    </v-main>

    <v-footer app color="transparent" height="90" inset>
      <chat-input v-on:send-msg="messages.push($event)" />
    </v-footer>
  </v-app>
</template>

<script>
import ChatInput from '@/components/ChatInput'
import ChatWindow from '@/components/ChatWindow'

export default {
  components: { ChatWindow, ChatInput },
  props: {
    source: String,
  },
  data: () => ({
    drawer: null,
    messages: [],
  }),
}
</script>

<style scoped>
#chat {
  overflow: hidden;
}
</style>
