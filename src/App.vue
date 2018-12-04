<template>
  <div>
    
    <forms :fields="fields1" 
    header='hello' 
    @eventName="parentEvent"
    ></forms>
    
    <forms/>
        
    <ul>
       <li v-for='(item, index) in items' :key='index'>
       {{ item }}
       </li>
    </ul>
    
  </div>
</template>

<script>

import forms from './components/forms.vue'

export default {
  name: 'app',
  data () {
  return {
      
      
      fields1: ['text', 'radio', 'checkbox', 'submit'],
      fields2: ['text', 'text', 'submit'],
      fields3: ['text', 'checkbox', 'submit'],
      items: []
      
  }
  },
  methods: {
      parentEvent(value){
         this.items.push(value)
      }

  },
  computed: {

  },
  components: {
    forms
  }
}
</script>


<style>
</style>