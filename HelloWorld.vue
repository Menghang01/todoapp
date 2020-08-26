<template>
    <div class="main">
        <div class="header">
      <h3>
        <b>Vue Jsss To do App</b>
      </h3>

      <hr />

    </div>
      <div class="list">
      <label for="title">Title</label>
      <input type="text" id="title" v-model="title">

      <label for="title">Project</label>
      <input type="text" id="title" v-model="project">

      <button @click="add()" id = "Add">Add</button>
    </div>

      <h2>Pendings Lists</h2> 

    <div class="display">
      <ul>
        <li :key="todo" v-for="(todo,i) in existingApp" class="pending">
          <router-link to="/detail" class="link"><div> {{i+1}} {{todo.text}}</div> </router-link>
          <div class="project"> Project : {{todo.project}}</div>
          <div class="delete"> 
            <ion-icon class="icon" name="trash-outline" @click="deleteX(i)"></ion-icon>
          </div>


          <div @click = "done()" id = "status" class="status" v-bind:class="{already:todo.pending}">
            Pending
          </div>
        </li>

              
       
<router-view />


      </ul>
    </div>



    </div>
</template>

<script>
export default {
  name: "app", 
  data () {
     return {
       title: '', 
       project: '', 
       pending: false, 
       existingApp: [
         {
           text: "Have Sex", 
           project: "PornHub", 
           pending: false, 
         }, 
       ]
     }
  }, 
  methods: {
    add(){
      this.existingApp.push({
        text: this.title, 
        project: this.project, 
        pending: false, 
      })
    }, 

    deleteX(i){
      this.existingApp.splice(i,1)
    }, 
    done(){
      alert("Done")
    },
  } 

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}

#Add {
  outline: none;
  background-color: orange;
  border: none;
  border-radius: 10px;
  padding: 10px;
  margin-top: 10px;
  width:100px;
  font-size: 15px;
  color: white;
}
.delete{
  display: flex;
  justify-content: flex-end;
  font-size: 20px;
}

 .link {
  color: black;
  text-decoration: none;
} 

.already {
  color: green;
}

.icon {
  cursor: pointer;
}
.pending {
  width: 200px;
  height: 100px;
  padding: 10px;
  border-radius: 10px;
  font-size: 15px;
  border: 2px solid rgb(237,237,237);
  font-weight: bold;
  line-height: 20px;
  position: relative;
  margin-bottom: 10px;
}
.status{
  padding: 10px 0;
  text-align: center;
  border: 1px solid red;
  width: 99%;
  border-radius: 10px;
  color: red;
  cursor: pointer;
}

#status{
  position: absolute;
  bottom: 0;
  left: 0;
}
.project {
  opacity: 0.4;
}
ul {
  list-style: none;
}
#Add:active {
  transform: translateY(-5px);
}
.list {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-left: 40px;
}

.list > input {
  border-radius: 10px;
  outline: none;
  border: 1px solid aqua;
  padding: 10px; 
  width: 200px;
}

label {
  margin-right: 10px;
}
</style>
