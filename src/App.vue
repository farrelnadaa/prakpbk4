<template>
  <div class="parent">
    <h1>Parent Component</h1>
    <p>Data from Child: {{ childData }}</p>
    <ChildComponent @send-data="updateData">
      <template #default="{ message }">
        <p>Slot Content: {{ message }}</p>
      </template>
    </ChildComponent>
  </div>
</template>

<script>
import ChildComponent from './components/ChildComponent.vue';

export default {
  components: {
    ChildComponent
  },
  data() {
    return {
      childData: ''
    };
  },
  methods: {
    updateData(data) {
      this.childData = data;
    }
  }
};
</script>

<style scoped>
.parent {
  border: 2px solid #333;
  padding: 20px;
  margin: 10px;
  background-color: #f9f9f9;
}
.parent h1 {
  color: #333;
}
</style>
