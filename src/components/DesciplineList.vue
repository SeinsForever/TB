<script>
export default {
  props: {
    discipline: {
      type: Array,
      required: true,
    },
  },
};
</script>

<template>
  <div>
    <p><Strong>Select descipline</Strong></p>
    <div class="card" v-for="item in discipline" :key="item">
      <div><strong>Title:</strong> {{ item.title }}</div>
      <div><strong>Body:</strong> {{ item.body }}</div>
    </div>
  </div>
</template>

<style scoped>
.card {
  margin: 15px;
  padding: 15px;
  border: 1px solid teal;
}
</style>
