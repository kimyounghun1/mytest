<template>
  <div id="app">

    <h1>CONTACT</h1>
    
    <form v-on:submit.prevent="onSubmit">
      SEARCH : <input type="text" v-model="search"/><br/>
      NAME : <input type="text" v-model="inputName"/>
      PHONE NUMBER CLONE : <input type="text" v-model="inputNumber"/>
      <input type="submit" value="ADD" v-on:click="addInput"/>
    </form>

    <p v-for="list in filtered" :key="list.id">
      <Contact v-bind:name="list.name" v-bind:phoneNumber="list.phoneNumber"></Contact>
    </p>

  </div>
</template>


<script>

import Contact from './components/Contact.vue'

export default {
  /*name: 'app',*/
  components: {
    Contact
  },

  data(){
    return {
      search:"",
      inputName:"", 
      inputNumber:"",
      lists:[],
      index:0
    }
  },

  methods: {
    addInput(){
      this.index += 1
      this.lists.push({
        id:this.index,
        name:this.inputName,
        phoneNumber:this.inputNumber
      })
      
      this.inputName = ""
      this.inputNumber = ""
    }
  },

  computed: {
    filtered:function(){
      let setFilter = this.search;
        return this.lists.filter(function(list){
          return list.name.includes(setFilter) || list.phoneNumber.includes(setFilter)
        })
    }
  }
}
</script>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>*/