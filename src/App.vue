<template>
  <div id="app">
    <Home></Home>
  </div>
</template>

<script>
  import Home from './components/Home'
  import Itunes from '@/components/Itunes'
  import Mytunes from '@/components/Mytunes'

  export default {
    name: 'app',
    components: {
      Home,
      Itunes,
      Mytunes
    }
  }

</script>

<style>

</style>