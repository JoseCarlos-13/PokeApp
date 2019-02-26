<template>
  <div>
  <el-input placeholder="Please input" v-model="search" class="inputbar" >
    <el-button slot="append" icon="el-icon-search"></el-button>
  </el-input>
</div>
</template>

<script>

export default {
  data () {
    return {
      search: ''
    }
  },

  props: ['getPokemon']}
</script>

<style>
  .inputbar{
    margin-top: 10px;
    width: 460px;
    margin-left: 1035px;
  }
</style>
