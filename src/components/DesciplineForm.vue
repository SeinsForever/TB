<script>
  export default{
    data(){
      return{
        newDiscipline:{
          title:"",
          body:"",
        },
      }
    },
    methods: {
      createDescipline(){
        this.newDiscipline.id = Date.now();
        this.$emit('create', this.newDiscipline);
        this.newDiscipline = {
          title: "",
          body: "",
        };
      }
    }
    
  }
</script>
<template>
  <div>
    <h4>Add new discipline</h4>
    <form @submit.prevent>
      <input 
        v-model="newDiscipline.title"
        class="input" 
        type="text" 
        placeholder="Title">
      <input 
        v-model="newDiscipline.body"
        class="input" 
        type="text" 
        placeholder="Body">
      <button class="btn" @click="createDescipline">ADD</button>
    </form>
  </div>
</template>

<style scoped>
  form{
    display: flex;
    flex-direction: column;
    margin: 15px;
  }
  .input{
    width: 100%;
    padding: 10px 15px;
    border: 1px solid teal;
  }
  .btn{
    margin-top: 15px;
    padding: 10px 15px;
    align-self: flex-end;
    background: none;
    color: teal;
    border: 1px solid teal;
  }
</style>