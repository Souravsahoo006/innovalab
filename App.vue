<template>
  <div style="text-align: center;">
    <div><h1>Parent Componnet</h1></div>
    <div>{{ childMessage }}</div>
    <childComponent :messageFromParent="parentMessage" :dataFromChild="getDataFromChild"/>
    <ChildComponentTwo :childMessageTwo = "childMessage"/>
  </div>
  <div style="margin-top: 51px;">
    <h1 style="margin-left: 90px;">Dyanamic Form</h1>
    <DyanamicForm/>
  </div>
</template>

<script>
import DyanamicForm from './components/DyanamicForm.vue';
import childComponent from './components/childComponent.vue'
import ChildComponentTwo from './components/childComponentTwo.vue';

export default {
  name: 'App',
  data() {
      return {
        parentMessage: 'Hello from the parent!',
        childMessage : ""
,
      };
    },
  components: {
    childComponent,
    ChildComponentTwo,
    DyanamicForm
},
  methods:{
    getDataFromChild(name){
      this.childMessage=name
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
