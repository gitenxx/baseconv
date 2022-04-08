<template>
  <q-page class="flex flex-center">
    <div>
          <InputPage />
        </div>
  </q-page>
</template>

<script>
// import { defineComponent } from 'vue'

// export default defineComponent({
//   name: 'IndexPage'
// })

import InputPage from "../components/InputPage";
export default {
  name: 'IndexPage',
  components: {InputPage}
}
</script>

