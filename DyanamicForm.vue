<template>
    <div class="container mt-4">
     <div class="card">
       <div class="card-body">
        <div  v-for="item,index in form" :key="item">
            <h3>Item {{ index+1 }}</h3>
           <div class="row">
             <div class="col-sm-5">
               <label>Name</label>
               <input type="text" class="form-control" v-model="item.name" >
             </div>
             <div class="col-sm-5 ">
               <label>checkbox</label>
               <input type="checkbox" class="form-check" v-model="item.checkBox">
             </div>
             <div class="col-sm-5">
               <label>Enter your DOB</label>
               <input type="date" class="form-control" v-model="item.dob">
             </div>
             <div class="col-sm-2 pt-4">
               <button type="button" class="btn btn-danger btn-sm" @click="removeRow(index)">x</button>&nbsp;
               <button type="button" class="btn btn-success btn-sm" @click="addRow">+</button>
             </div>
           </div>
        </div>
           <button type="button" class="btn btn-success mt-3" @click="saveItem">Save</button>
       </div>
     </div>
    </div>
  </template>
  <script>
  import { reactive } from 'vue'
  import axios from 'axios'
  export default {
    name: 'DynamicForm',
    data(){
      const form = reactive([
        { name : '', checkBox:'',dob:''}
      ])
  
      const addRow = () => {
        form.push({ name : '', checkBox:'',dob:''})
      }
  
      const removeRow = (index) =>{
        if(form.length > 1){
          form.splice(index,1)
        }
      }
  
      const saveItem = () =>{
        // axios
        // axios.post('items',form).then(res=>{
        //   console.log(res);
        // })
        axios.post("http://localhost:3000/blocks",this.item.name,this.item.checkbox,this.item.dob
        )
      }
      return{
        form,
        addRow,
        saveItem,
        removeRow,
      }
    }
  }
  </script>