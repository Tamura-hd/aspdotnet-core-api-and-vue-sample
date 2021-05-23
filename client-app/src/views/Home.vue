<template>
  <div class="home">
    <HelloWorld message="Welcome to ASP.NET Core and Vue.js App."/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>
