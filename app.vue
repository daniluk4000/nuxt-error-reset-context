<template>
  <div @click="navigateTo('/?error=1', {external: true})">
    Click to reload with error<br><br>

    State: {{store.state}}
  </div>
</template>

<script setup>
import {useStore} from "~/store";
import {showError} from "#app";

const store = useStore()
store.state = 'bar'
console.log(store.state)

if(useRoute().query.error) showError({
  statusCode: 500
})
</script>
