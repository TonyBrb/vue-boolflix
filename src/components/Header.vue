<template>
  <div>
    <div class="logo">
      <img src="../assets/img/boolflix-logo.png" alt="Boolflix">
    </div>
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
    height: 50px;
    margin-bottom: 0;
    background-color: black;
    display: flex;
    align-items: center;
    justify-content: space-between;

    .logo{
      width: 100px;
      margin-left: 8%;
      img{
        width: 100%;
      }
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