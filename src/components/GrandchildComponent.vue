<template>
    <div class="grandchild">
      <h3>Grandchild Component</h3>
      <button @click="sendDataToChild">Send Data to Child</button>
      <slot :message="slotMessage"></slot>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        slotMessage: 'Message from Grandchild Slot'
      };
    },
    methods: {
      sendDataToChild() {
        this.$emit('send-grandchild-data', 'Data from Grandchild');
      }
    }
  };
  </script>
  
  <style scoped>
  .grandchild {
    border: 2px solid #999;
    padding: 10px;
    margin: 10px;
    background-color: #eef;
  }
  .grandchild h3 {
    color: #999;
  }
  .grandchild button {
    background-color: #28a745;
    color: white;
    border: none;
    padding: 8px;
    cursor: pointer;
  }
  .grandchild button:hover {
    background-color: #218838;
  }
  </style>
  