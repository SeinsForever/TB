<script>
  import DesciplineList from "@/components/DesciplineList.vue"
  import DesciplineForm from "@/components/DesciplineForm.vue"
  export default {
    components: {
        DesciplineForm, DesciplineList
    },
    data() {
      return {
        discipline: [
          {id: 1, title: "Электробезопасность", body: "Система организационных мероприятий и технических средств, предотвращающих вредное и опасное воздействие на работающих электрического тока, электрической дуги, электромагнитного поля и статического электричества."},
          {id: 2, title: "Охрана труда", body: "Система сохранения жизни и здоровья работников в процессе трудовой деятельности, включающая в себя правовые, социально-экономические, организационно-технические, санитарно-гигиенические, лечебно-профилактические, реабилитационные и иные мероприятия, образующие механизм реализации конституционного права граждан на труд (ст. 37 Конституции РФ) в условиях, отвечающих требованиям безопасности и гигиены."},
          {id: 3, title: "СИЗ", body: "Изделия, предназначенные для защиты кожи и органов дыхания от воздействия отравляющих веществ и/или вредных примесей в воздухе."},
        ],
      }
    },
    methods: {
      createDiscipline(newDiscipline) {
        this.discipline.push(newDiscipline)
      }
    }
  }
</script>

<template>
  <div class="row row-cols-auto m-3 g-4">
    <!--  -->
      <div class="col-sm-12 col-md-6">
        <div class="p-3 rounded-3 shadow-sm">
          <div class="col col-auto mb-2">
            <button type="button " class="btn" style="color: #0058A9;background-color: #DDE8EE;">В процессе</button>
          </div>

          <div class="col  h4  mb-2">Проверка №0001</div>

          <div class="col text-start">
            <table class="table">
              <tbody>
                <tr>
                  <td>Объект</td>
                  <td>Склад</td>
                </tr>
                <tr>
                  <td>Дата</td>
                  <td>01.01.2023</td>
                </tr>
                <tr>
                  <td style="border-bottom: none;">Выявленные нарушения</td>
                  <td style="border-bottom: none;">3</td>
                </tr>
              </tbody>
            </table>
            <!-- <div class="row row-cols-2">
              <div class="col-8">Объект</div>
              <div class="col-auto">Склад</div>
              <div class="col-8">Дата</div>
              <div class="col-auto">01.01.2023</div>
              <div class="col-8">Выявленные нарушения</div>
              <div class="col-auto">3</div>
            </div> -->
          </div>
        </div>
      </div>

      
      
    <!--  -->
  </div>
  <div class="app">
    <DesciplineForm @create="createDiscipline"/>
    <DesciplineList :discipline="discipline" />
    
  </div>
  
</template>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  .app{
    padding: 20px;
  }
  
</style>
