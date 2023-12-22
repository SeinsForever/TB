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
      if (this.newInspection.objectOfInspection) {
        this.newInspection.id = Date.now();
        this.newInspection.date = Date.now();
        this.newInspection.numberOfViolations = 0;
        this.newInspection.status = 0;
        this.$emit("create", this.newInspection);
        this.newInspection = {
          objectOfInspection: "",
          date: "",
          numberOfViolations: 0,
          status: 0,
        };
      }
    },
  },
};
</script>
<template>
  <div class="">
    <div class="p-4 col-sm-auto rounded-3 shadow-sm">
      <form @submit.prevent>
        <div class="text-center">
          <label for="exampleInputEmail1" class="form-label h3"
            ><div class="">Новая проверка</div></label
          >
        </div>
        <div class="form-floating mb-3">
          <input
            v-model="newInspection.objectOfInspection"
            type="name"
            class="form-control"
            id="placeName"
            placeholder="name@example.com"
            required
          />
          <label for="floatingInput">Название объекта</label>
          <div class="invalid-feedback">Please choose a username.</div>
        </div>

        <div
          class="d-flex justify-content-start align-items-center border rounded-3 mb-3"
        >
          <div
            class="p-2 rounded-start-3"
            style="background-color: rgba(248, 249, 250, 1)"
          >
            <input
              type="checkbox"
              class="form-check-input"
              id="exampleCheck1"
              value="Электробезопасность"
            />
          </div>
          <label class="mx-3" for="exampleCheck1">Электробезопасность</label>
        </div>
        <div
          class="d-flex justify-content-start align-items-center border rounded-3 mb-3"
        >
          <div
            class="p-2 rounded-start-3"
            style="background-color: rgba(248, 249, 250, 1)"
          >
            <input
              type="checkbox"
              class="form-check-input"
              id="exampleCheck2"
              value="Электробезопасность"
            />
          </div>
          <label class="mx-3" for="exampleCheck2">Охрана труда</label>
        </div>
        <div
          class="d-flex justify-content-start align-items-center border rounded-3 mb-3"
        >
          <div
            class="p-2 rounded-start-3"
            style="background-color: rgba(248, 249, 250, 1)"
          >
            <input
              type="checkbox"
              class="form-check-input"
              id="exampleCheck3"
              value="Электробезопасность"
            />
          </div>
          <label class="mx-3" for="exampleCheck3">СИЗ</label>
        </div>
        <button
          type="submit"
          class="btn btn-primary mb-3"
          @click="createInspection"
        >
          Создать проверку
        </button>
      </form>
    </div>
  </div>
</template>
