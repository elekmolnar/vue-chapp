<template>
  <v-container fluid>
    <v-row align="start" justify="start">
      <v-col cols="12" md="12" sm="12">
        <v-virtual-scroll :item-height="80" :items="messages" height="800px">
          <template v-slot="{ item }">
            <v-list-item :key="item">
              <v-list-item-avatar color="grey darken-1"></v-list-item-avatar>

              <v-list-item-content class="list-item-container">
                <v-list-item-title>Message</v-list-item-title>

                <v-list-item-subtitle>
                  {{ item }}
                </v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>

            <v-divider></v-divider>
          </template>
        </v-virtual-scroll>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'ChatWindow',
  props: {
    messages: {
      type: Array,
    },
  },
}
</script>

<style scoped>
.list-item-container {
  text-align: left;
}
</style>
