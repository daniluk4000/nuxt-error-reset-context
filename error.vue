<template>
  <div @click="navigateTo('/', {external: true})">
    Click to clear error<br><br>

    State: {{store.state}} (should be bar)
  </div>
</template>
<script lang="ts">
import {useStore} from "~/store";

export default defineComponent({
  props: {
    error: {
      type: Object,
    },
  },
  setup() {
    const store = useStore()

    return {
      store
    }
  }
})
</script>
