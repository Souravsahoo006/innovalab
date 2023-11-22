<template>
    <div>
      <h2>Child Component Two</h2>
      <p>{{ childMessageTwo }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data () {
        return {
            messageFromChild:"Bye From  child!!"
        }
    },
    props: {
        childMessageTwo: String,
    },
  };
  </script>