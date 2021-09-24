<template>
  <client-only>
    <v-ckeditor v-model="text" />
  </client-only>
</template>

<script>
export default {
  data() {
    return {
      text: 'Hello World!!',
    }
  },
}
</script>
