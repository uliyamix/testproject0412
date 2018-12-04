<template>
  <div class="container">
    
    <div>{{header}}</div>
    
    <form>
    <input
    v-for="(v, i) in fields" 
    v-model='input'
    :type="v" 
    :key="i"
    @keyup.enter="handleEnter"
    />

    </form>
    
    
  </div>
</template>


<script>
export default {
name: 'forms',
data(){
  return{
       input: ''
    }
  },
  
  props: {
  'fields': Array,
  'header': String,
  'footer': {
     type: Number
  }
  },
  methods: {
     handleEnter(event){
     event.preventDefault()
     this.$emit('eventName', this.input) //передаём родителю
     this.input = ''       
  }
  }
}
</script>

<style scoped>
.container{
  width: 50%;
  margin: auto;
  background-color: lightgray;
  box-shadow: 1px 2px 2px grey;
}
</style>