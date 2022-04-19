<template>
  <div class="q-pa-md" style="max-width: 300px">
    <h3>Input base64 string here</h3>
    <q-input
      v-model="text"
      filled
      type="textarea"
      v-on:change="(event) => decodeBase64(event)"
    />
  </div>
</template>

<script>
let Base64 = require("js-base64").Base64;

import { ref } from "vue";

export default {
  name: "InputPage",
  setup() {
    return {
      text: ref(""),
    };
  },
  methods: {
    decodeBase64() {
      console.log(Base64.decode(this.text));
    },
  },
};
</script>

<!-- TODO: error handler -->
