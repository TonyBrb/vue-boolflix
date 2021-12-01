<template>
  <div>
    <span>BOOLFLIX</span>
    <div class="search-bar">
      <input type="text" placeholder="Inserisci il film da cercare">
      <button class="btn">Cerca</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>
  div{
    height: 50px;
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
      padding: 11px;
    }

    input{
      line-height: 35px;
    }
  }
</style>