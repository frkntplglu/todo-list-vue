<template>
  <ul>
    <li v-for="(todo, index) in todos" v-on:click="deleteTodo(index)"> <b>{{ index + 1 }})</b> {{ todo }}</li>
  </ul>
</template>
<script>
export default {
  props : ['todos'],
  data(){
    return {

    }
  },
  methods: {
    deleteTodo(index){
      this.todos.splice(index,1);
      if(this.todos.length == 0){
        this.$parent.isEmpty = true;
      }
    }
  }

}
</script>
<style lang="">
  ul{
    list-style: none;
    margin: 20px 0 0 0;
    padding: 0;
  }
  ul li{
    border-bottom: 1px solid #ddd;
    padding: 10px;
    cursor: pointer;
  }
  ul li:hover{
    text-decoration: line-through;
  }
</style>