<template>
  <div id="app">
    <h1 class="title">{{title}}</h1> <!--se renderiza-->
    <div class="container">
      <div class="form">
        <p class="form-content">Tarea</p>
        <input class="form-content" type="text" v-model="task" placeholder="Ingrese nueva tarea">
        <button class="form-content" @click="add">Crear</button>
      </div>
      <div>
        <h2 class="title">Lista</h2>
        <ul v-for="(task, index) in tasks" :key="index">
          <li>{{index}}: {{task}}</li>
        </ul>
      </div>    
    </div> 
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){     //se crea data
    return {
      title: "Crea una nueva tarea",
      task:"",
      tasks:[]
    }
  },
  methods: {
    add:function(){
      this.tasks.push(this.task)
      this.task=""
    }
  }
}
</script>

<style>
*{
  background:hsla(0, 0%, 100%, 0.932); 
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

.title{
  color: gray;
  font-size: 40px;

  padding: 20px 0;
}

.container{
  width: 90%;
  margin: 0 auto;
}

.form{
  display: flex;
  justify-content: center;  
}

.form-content{
  margin: 0 10px;

}

input{
  width: 250px;
  color: grey;
  font-size: 15px;
}

p, li{
  color: black;
  font-weight: bold;
  font-size: 25px;
}

button{
  font-size:15px ;
  background: rgb(223, 220, 220);
  border-radius: 5px;
}

ul{
  display: flex;
  margin-left:40%;
  /* justify-content: center;     */
}

</style>
