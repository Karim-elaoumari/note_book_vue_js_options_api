<script>
import about from './components/about.vue';
import note from './components/note.vue';
export default {

  components:{ about,note},
  
  data() {
    return {
      component: 'about',
      tabs:['about','note'],
    }
  },
  beforeCreate(){
   
      alert('beforeCreate')
  },
  created() {
    alert('afterCreate')
  },
  beforeMount(){
    alert('beforeMount')
  },
  mounted() {
    alert('Mounted')
  },
  beforeUpdate(){
    alert('before update')
  },
  updated(){
    alert('after  update')
  }
}
</script>

<template>
  <header>
   <!--  dynamic classses directives  attribute binding $emit  spread operator destructing -->
  </header>
  <div>
    <button v-for="tab in tabs" :key="tab" @click="component=tab">{{tab}} </button>
  </div>
 
<KeepAlive>
   <component  :is="component"/>
</KeepAlive>
</template>
<style scoped>

</style>



