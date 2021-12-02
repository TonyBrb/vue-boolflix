<template>
  <div>
    <span>BOOLFLIX</span>
    <div class="search-bar">
      <input type="text" v-model="text" placeholder="Inserisci il film da cercare">
      <button class="btn" @click="$emit('textToSearch', text)">Cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data(){
    return{
      text:''
    }
  }
}
</script>

<style lang="scss" scoped>
  div{
    height: 70px;
    margin-bottom: 0;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: space-between;

    span{
      font-size: 48px;
      color: red;
      font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    }
    
    button{
      padding: 12px;
      background-color: red;
      color: white;
      border: none;
    }

    input{
      line-height: 35px;
    }
  }
</style>