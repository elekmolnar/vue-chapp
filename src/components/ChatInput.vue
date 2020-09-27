<template>
  <v-row align="center" justify="start">
    <v-col cols="12" md="11" sm="8">
      <v-text-field
        v-model.lazy="value"
        :no-resize="true"
        :outlined="true"
        :rows="1"
        :rules="rules"
        :value="value"
        clear-icon="mdi-close-circle"
        clearable
        counter
        dense
        flat
        prepend-icon="mdi-comment"
        solo
        v-on:keyup.enter="sendMsg"
      ></v-text-field>
    </v-col>
    <v-col align-self="baseline" cols="12" md="1" sm="8">
      <v-btn color="primary" dark large v-on:click="sendMsg">
        Send
      </v-btn>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'ChatInput',
  data: () => ({
    rules: [v => v.length <= 200 || 'Max 200 characters'],
    value: '',
  }),
  methods: {
    sendMsg: function() {
      this.$emit('send-msg', this.value)
      this.value = ''
    },
  },
}
</script>

<style scoped></style>
