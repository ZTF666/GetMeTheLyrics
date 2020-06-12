<template>
  <v-footer fixed app class="justify-center mt-10">
    <span>
      <strong>{{author}}</strong>
      &nbsp;&nbsp;with&nbsp;❤️&nbsp;&nbsp;&copy; {{ new Date().getFullYear() }}
    </span>
  </v-footer>
</template>

<script>
export default {
  data() {
    return {
      author: '</💻>    ZTF'
    }
  }
}
</script>

<style>
</style>