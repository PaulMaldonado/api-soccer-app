<template>
  <div class="home">
    <Videos />
  </div>
</template>

<script>
// @ is an alias to /src
import Videos from '@/components/Videos.vue'
export default {
  name: 'Home',
  components: {
    Videos
  }
}
</script>
