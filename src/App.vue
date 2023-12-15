<script>
import DesciplineList from "@/components/DesciplineList.vue";
import DesciplineForm from "@/components/DesciplineForm.vue";
import InProccessButton from "@/components/InProccessButton.vue";
import InProccessButton from './components/InProccessButton.vue';

export default {
  components: {
    DesciplineForm,
    DesciplineList
    InProccessButton,
  },
  data() {
    return {
      discipline: [
        {
          id: 1,
          title: "Электробезопасность",
          body: "Система организационных мероприятий и технических средств, предотвращающих вредное и опасное воздействие на работающих электрического тока, электрической дуги, электромагнитного поля и статического электричества.",
        },
        {
          id: 2,
          title: "Охрана труда",
          body: "Система сохранения жизни и здоровья работников в процессе трудовой деятельности, включающая в себя правовые, социально-экономические, организационно-технические, санитарно-гигиенические, лечебно-профилактические, реабилитационные и иные мероприятия, образующие механизм реализации конституционного права граждан на труд (ст. 37 Конституции РФ) в условиях, отвечающих требованиям безопасности и гигиены.",
        },
        {
          id: 3,
          title: "СИЗ",
          body: "Изделия, предназначенные для защиты кожи и органов дыхания от воздействия отравляющих веществ и/или вредных примесей в воздухе.",
        },
      ],
    };
  },
  methods: {
    createDiscipline(newDiscipline) {
      this.discipline.push(newDiscipline);
    },
  },
};
</script>

<template>
  <div>
    <div class="row m-3 g-4">
      <div class="col-xs-12 col-sm-12 col-md-6 col-xl-4 col-xxl-3">
        <div class="p-4 rounded-3 shadow-sm">
          <div class="col mb-3">
            <div class="app">
              <InProccessButton />
            </div>
          </div>

          <div class="col h4 mb-3">Проверка №0001</div>

          <div class="col text-start">
            <table class="table mb-0">
              <tbody>
                <tr>
                  <td class="pt-0">Объект</td>
                  <td class="pt-0">Склад</td>
                </tr>
                <tr>
                  <td>Дата</td>
                  <td>01.01.2023</td>
                </tr>
                <tr>
                  <td style="border-bottom: none">Выявленные нарушения</td>
                  <td style="border-bottom: none">3</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <!--  -->
    </div>
    <div class="app">
      <in-proccess-button />
      <DesciplineForm @create="createDiscipline" />
      <DesciplineList :discipline="discipline" />
    </div>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
</style>

<!-- <div class="row row-cols-2">
              <div class="col-8">Объект</div>
              <div class="col-auto">Склад</div>
              <div class="col-8">Дата</div>
              <div class="col-auto">01.01.2023</div>
              <div class="col-8">Выявленные нарушения</div>
              <div class="col-auto">3</div>
            </div> -->
