<template>
    <div>
      <h2>Child Component</h2>
      <p>{{ messageFromParent }}</p>
      <button @click="dataFromChild(messageFromChild)">Send Data to Parent</button>
    </div>
  </template>
  
  <script>
  export default {
    data () {
        return {
            messageFromChild:"Bye From  child!!!"
        }
    },
    props: {
      messageFromParent: String,
      dataFromChild: Function
    },
  };
  </script>
  