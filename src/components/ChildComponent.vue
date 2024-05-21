<template>
    <div class="child">
      <h2>Child Component</h2>
      <p>Data from Grandchild: {{ grandchildData }}</p>
      <button @click="sendDataToParent">Send Data to Parent</button>
      <GrandchildComponent @send-grandchild-data="updateGrandchildData">
        <template #default="{ message }">
          <p>Grandchild Slot Content: {{ message }}</p>
        </template>
      </GrandchildComponent>
    </div>
  </template>
  
  <script>
  import GrandchildComponent from './GrandchildComponent.vue';
  
  export default {
    components: {
      GrandchildComponent
    },
    data() {
      return {
        grandchildData: ''
      };
    },
    methods: {
      sendDataToParent() {
        this.$emit('send-data', 'Data from Child');
      },
      updateGrandchildData(data) {
        this.grandchildData = data;
      }
    }
  };
  </script>
  
  <style scoped>
  .child {
    border: 2px solid #666;
    padding: 15px;
    margin: 10px;
    background-color: #eef;
  }
  .child h2 {
    color: #666;
  }
  .child button {
    background-color: #007bff;
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
  }
  .child button:hover {
    background-color: #0056b3;
  }
  </style>
  