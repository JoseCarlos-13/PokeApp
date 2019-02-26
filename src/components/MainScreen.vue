<template>
  <div>
    <menubar></menubar>
    <container></container>
  </div>
</template>

<script>
import menubar from './menubar'
import container from './Containerapi'

export default {
  components: {
    'menubar': menubar,
    'container': container
  }
}
</script>

<style>
  body {
    color: white;
    background-color: red;
  }
</style>
