<script>
export default {
  data() {
    return {
      newInspection: {
        objectOfInspection: "",
        date: "",
        numberOfViolations: 0,
        status: 0,
      },
    };
  },
  methods: {
    createInspection() {
      this.newInspection.id = Date.now();
      this.$emit("create", this.newInspection);
      this.newInspection = {
        objectOfInspection: "",
        date: "",
        numberOfViolations: 0,
        status: 0,
      };
    },
  },
};
</script>
<template>
  <div>
    <h4>Add new discipline</h4>
    <form @submit.prevent>
      <input
        v-model="newInspection.objectOfInspection"
        class="input"
        type="text"
        placeholder="objectOfInspection"
      />
      <input
        v-model="newInspection.date"
        class="input"
        type="date"
        placeholder="Body"
      />
      <input
        v-model="newInspection.numberOfViolations"
        class="input"
        type="number"
        placeholder="0"
      />
      <input
        v-model="newInspection.status"
        class="input"
        type="number"
        placeholder="0"
      />
      <button class="btn" @click="createInspection">ADD</button>
    </form>
  </div>
</template>

<style scoped>
form {
  display: flex;
  flex-direction: column;
  margin: 15px;
}
.input {
  width: 100%;
  padding: 10px 15px;
  border: 1px solid teal;
}
.btn {
  margin-top: 15px;
  padding: 10px 15px;
  align-self: flex-end;
  background: none;
  color: teal;
  border: 1px solid teal;
}
</style>
