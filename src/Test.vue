<template>
  <div v-if="couldBeUndefined">
    <span v-for="x in couldBeUndefined" :key="x">
      {{ couldBeUndefined.length }}
    </span>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue"


export default defineComponent( {
  props: {
    foo: Boolean
  },
  computed: {
    couldBeUndefined(): string[] | undefined {
      if (this.foo) {
        return ['thing', 'sing']
        } else {
          return undefined
        }
    }
  }
})
</script>