<template>
  <div id="app">
  <router-view/>
  </div>
</template>

<script>
export default {
  name: "Wtf", 
  components: {
  }


}
</script>

<style>

*{
    font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif

}


.header{
  margin-left: 20px;
}


#app {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}



</style>
