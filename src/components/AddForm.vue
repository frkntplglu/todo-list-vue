<template>
  <div class="add-task">
    <input type="text" placeholder="Add your task" class="input" v-on:keyup.enter="addTask" v-model="task">
    <button class="button" v-on:click="addTask">ADD TASK</button>
  </div>
</template>

<script>
export default {
  data(){
    return {
      task : ''
    }
  },
  methods : {
    addTask(){
      this.$emit('taskAdded',this.task);
      document.querySelector('.input').value = '';
    }
  }
}
</script>
<style lang="">
  .add-task{
    display:flex;
    justify-content: space-between;
  }
  .input{
    width:calc(100% - 200px);
    box-sizing: border-box;
    padding: 0 20px;
    font-size:14px;
    border:1px solid #ddd;
    border-radius: 5px;
    outline: #ff9f1a;
    transition: 300ms;
  }
  .input:focus{
    border-color:#ff9f1a;
    box-shadow:0 0 5px #ff9f1a;
  }
  .button{
    background: #ff9f1a;
    color:#fff;
    font-size:16px;
    font-weight: 600;
    border:none;
    border-radius:5px;
    cursor:pointer;
    width:190px;
    padding: 15px 20px;
    transition: 300ms;
  }
  .button:hover{
    background: #70b500;
  }
</style>