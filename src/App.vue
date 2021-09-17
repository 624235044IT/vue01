<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <br/>
    <span> {{ message1 }}  </span> <br/>
    <span v-text="message2"> </span>
    <hr/>
    <span> {{ counter }} </span> <br/>
    <button v-on:click ="counter=counter+1"> +</button>
    <button v-on:click ="minus">-</button>
    <hr/>
    <span> {{ message3 }} </span> <br/>
    <input type="text" v-model="message3">
    <select v-model="message3">
      <option value="choice01">Hello 1 </option>
      <option value="choice02">Hello 2 </option>
      <option value="choice03">Hello 3 </option>
    </select><br/><br/>
    <textarea v-model="message3"></textarea>
    <hr/>
    
    <img v-bind:src="require(`@/assets/images/` +imagename)">  
    <select v-model="imagename">
      <option value="rac.jpg">image 1 </option>
      <option value="ca.jpg">image 2 </option>
    </select><br/><br/>
    <hr/>
    <h1 v-show="isGreeting"> Hello [!]</h1>
    <hr/>
    {{htmlText}}<br/><br/>
    <span v-html="htmlText"></span>
     <hr/>

  <div v-bind:key="emp.id" v-for="emp in employees">
    <b>Id</b>: {{emp.id}},<br/> 
    <b>Name</b>: {{emp.name}},<br/> 
    <b>Salary</b>:{{emp.Salary}},<br/><br/><br/> 
  </div>
  <hr/>
  <div v-bind:key="stu.id" v-for="stu in students">
    <b>studentId</b>:{{stu.id}},<br/> 
    <b>firstname</b>:{{stu.name}},<br/> 
    <b>lastName</b>:{{stu.lastName}},<br/>
    <b>score</b>:{{stu.score}},<br/><br/><br/> 
  </div>



    <input v-bind:type="inputtype" /> 
     





    
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>


<script>
//import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    //HelloWorld
  },
  data(){
    return{
      message1: "Hello World !!",
      message2: "Hell World Again !!",
      message3: "Nirachha Wanchitnai",
      inputtype:"radio" ,
      imagename: "rac.jpg",
      htmlText:"<b>HTML TEXT</b>&nbsp;",
      counter: 0,
      isGreeting: false,
      employees:[{"id":1,"name":"John","Salary":30000},
      {"id":2,"name":"Trump","Salary":10000},
      {"id":3,"name":"Peter","Salary":99000}],
      students:[{"id":624235044,"name":"Niracha","lastName": "Wanchitnai","score":20},
      {"id":624235034,"name":"Wirakran","lastName": "Somjan","score":25},
      {"id":624235036,"name":"Yada","lastName": "Binlateh","score":50},
      {"id":624235036,"name":"Kuasawan","lastName": "Kuji","score":30}]
      

    }
  },
  methods:{
    minus: function(){
      this.counter=this.counter-1
    }
  }
}
</script>






<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
