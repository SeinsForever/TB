<script>
import InProccessButton from "./InProccessButton.vue";
import SuccessButton from "./SuccessButton.vue";
export default {
  components: {
    InProccessButton,
    SuccessButton,
  },
  props: {
    inspection: {
      type: Array,
      required: true,
    },
  },
};
</script>
<template>
  <div>
    <div class="row m-3 g-4">
      <div
        v-for="item in inspection"
        :key="item"
        class="col-xs-12 col-sm-12 col-md-6 col-xl-4 col-xxl-3"
      >
        <div class="p-4 rounded-3 shadow-sm">
          <div class="col mb-3 p-0">
            <SuccessButton v-if="item.status" />
            <InProccessButton v-else />
          </div>

          <div class="col h4 mb-3">Проверка №{{ item.id }}</div>

          <div class="col text-start">
            <table class="table mb-0">
              <tbody>
                <tr>
                  <td class="pt-0">Объект</td>
                  <td class="pt-0">{{ item.objectOfInspection }}</td>
                </tr>
                <tr>
                  <td>Дата</td>
                  <td>
                    {{ item.date }}
                  </td>
                </tr>
                <tr>
                  <td style="border-bottom: none">Выявленные нарушения</td>
                  <td style="border-bottom: none">
                    {{ item.numberOfViolations }}
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <!--  -->
    </div>
    <p v-if="!inspection.length">Вы не создали ни одной проверки</p>
  </div>
</template>
