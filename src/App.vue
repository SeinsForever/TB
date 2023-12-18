<script>
import DesciplineList from "@/components/DesciplineList.vue";
import DesciplineForm from "@/components/DesciplineForm.vue";
import InspectionList from "./components/InspectionList.vue";
import InspectionForm from "./components/InspectionForm.vue";

export default {
  components: {
    DesciplineForm,
    DesciplineList,
    InspectionList,
    InspectionForm,
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
      inspection: [
        {
          id: 1,
          objectOfInspection: "Склад №33",
          date: "27.05.2023",
          numberOfViolations: 3,
          status: 1,
        },
        {
          id: 2,
          objectOfInspection: "Склад №42",
          date: "05.09.2023",
          numberOfViolations: 6,
          status: 0,
        },
        {
          id: 3,
          objectOfInspection: "КПП",
          date: "11.10.2023",
          numberOfViolations: 0,
          status: 1,
        },
        {
          id: 4,
          objectOfInspection: "Офис 234",
          date: "20.10.2023",
          numberOfViolations: 2,
          status: 1,
        },
      ],
    };
  },
  methods: {
    createDiscipline(newDiscipline) {
      this.discipline.push(newDiscipline);
    },
    createInspecion(newInspection) {
      this.inspection.push(newInspection);
    },
  },
};
</script>

<template>
  <div class="app pt-0 ps-0 pe-0">
    <nav class="navbar navbar-expand-lg" style="background-color: #eef7f3">
      <div class="container-fluid">
        <a class="navbar-brand ms-3" href="#"
          ><svg
            width="35"
            height="35"
            viewBox="0 0 35 35"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <rect width="35" height="35" rx="3.96226" fill="#202B26" />
            <path
              d="M5.41432 11.5878V10.04H16.2205V11.5878H11.6898V24.4482H9.94503V11.5878H5.41432ZM18.9132 24.4482V10.04H27.6088V11.5878H20.658V16.0903H24.3163C25.3482 16.0903 26.2182 16.2592 26.9264 16.5969C27.6393 16.9346 28.1787 17.4106 28.5445 18.025C28.915 18.6395 29.1003 19.3641 29.1003 20.1989C29.1003 21.0338 28.915 21.7701 28.5445 22.408C28.1787 23.0459 27.6393 23.5454 26.9264 23.9065C26.2182 24.2677 25.3482 24.4482 24.3163 24.4482H18.9132ZM20.658 22.9286H24.3163C24.973 22.9286 25.5287 22.7973 25.9837 22.5346C26.4433 22.2673 26.7904 21.9249 27.0249 21.5075C27.2641 21.0854 27.3837 20.6398 27.3837 20.1708C27.3837 19.4813 27.1187 18.888 26.5887 18.3909C26.0587 17.889 25.3013 17.6381 24.3163 17.6381H20.658V22.9286Z"
              fill="#8EEFC5"
            />
          </svg>
        </a>
        <button
          class="navbar-toggler me-3"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" href="#">Главная страница</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Мои проверки</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Запланировать проверку</a>
            </li>
          </ul>
          <a class="nav-link d-flex flex-row align-items-center" href="#"
            >Китина Гильмуллина
            <svg
              class="ms-2 me-3"
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M12 12C14.7614 12 17 9.76142 17 7C17 4.23858 14.7614 2 12 2C9.23858 2 7 4.23858 7 7C7 9.76142 9.23858 12 12 12Z"
                stroke="#292D32"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M20.59 22C20.59 18.13 16.74 15 12 15C7.26003 15 3.41003 18.13 3.41003 22"
                stroke="#292D32"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
          </a>
        </div>
      </div>
    </nav>
    <div>
      <inspection-form @create="createInspecion" />
      <InspectionList :inspection="inspection" />
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
</style>

<!-- <div class="row row-cols-2">
              <div class="col-8">Объект</div>
              <div class="col-auto">Склад</div>
              <div class="col-8">Дата</div>
              <div class="col-auto">01.01.2023</div>
              <div class="col-8">Выявленные нарушения</div>
              <div class="col-auto">3</div>
            </div> -->
