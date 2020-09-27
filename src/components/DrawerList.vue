<template>
  <v-list dense>
    <v-list-item link>
      <v-list-item-action>
        <v-icon>mdi-home</v-icon>
      </v-list-item-action>
      <v-list-item-content>
        <v-list-item-title>
          <router-link to="/">Home</router-link>
        </v-list-item-title>
      </v-list-item-content>
    </v-list-item>
    <v-list-item link>
      <v-list-item-action>
        <v-icon>mdi-bus-stop-uncovered</v-icon>
      </v-list-item-action>
      <v-list-item-content>
        <v-list-item-title>Lounge</v-list-item-title>
      </v-list-item-content>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  name: 'DrawerList',
}
</script>

<style scoped></style>
