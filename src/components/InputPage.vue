<template>
  <div style="max-width: 300px">
    <h3>Input base64 string here</h3>
    <q-input
      v-model="text"
      filled
      type="textarea"
      v-on:change="(event) => decodeBase64(event)"
    />
  </div>
  <div>
    <q-field class="q-mt-lg" borderless label="Decoded:" stack-label>
      <template v-slot:control>
        <div class="self-center full-width no-outline" tabindex="10">
          {{ decodeBase64() }}
        </div>
      </template>
    </q-field>
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
      try {
        var decoded = Base64.decode(this.text);
        return decoded;
      } catch (err) {
        if (err.message == "The string to be decoded is not correctly encoded.")
          console.log(`Invalid encoding: ${this.text}.`);
      }
    },
  },
};
</script>
