<template>
  <client-only>
    <v-ckeditor v-model="text" />
  </client-only>
</template>

<script lang="ts">
import { Component, Vue } from 'nuxt-property-decorator'
@Component
export default class extends Vue {
  private text = 'Hello World!!'
}
</script>
