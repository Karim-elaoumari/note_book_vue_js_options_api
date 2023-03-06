<script>
export default {
  data() {
    return {
      newItem :"",
      title: 'todo list of today',
      items :[
        { 'id':0,'content':'start a free day with coffe' },
        { 'id':1,'content':'open my laptop and start planing'},
        { 'id':2,'content':'give the best of my power to finish my briefs and learn new thinks'}
      ]
    }
  },
  methods:{
    addNewItem(){
      if(this.newItem!=''){
        this.items.push({'id':this.items.length+1,'content':this.newItem}),
        this.newItem= ''
      }
    }
  }
}
</script>

<template>
  <main>
    <div style="width: 400px;border: 2px solid brown;"> 
      <input  type="text" v-model="newItem" placeholder="Add new todo item" >
      <button @click="addNewItem" v-bind:disabled="newItem.length==0">Add</button>
    </div>
    <div style="width: 400px;border: 2px solid brown;"> 
      <h2>{{ title }}</h2>
      <ul>
        <li v-for="item of items" :key="item.id"> {{ item.content }}</li>
      </ul>
    </div>
  </main>
</template>
<style scoped>

</style>