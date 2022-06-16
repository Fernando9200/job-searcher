<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="site logo" />
        <h1>Job Searcher</h1>
      </div>
      <div class="order">
        <button @click="handleClick('title')">Order by title</button>
        <button @click="handleClick('salary')">Order by salary</button>
        <button @click="handleClick('location')">Order by location</button>
      </div>
    </header>

    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "@/types/Job";
import OrderTerm from "@/types/OrderTerm";
import JobList from "./components/JobList.vue";
export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "Web Developer",
        location: "Houston",
        salary: 3000,
        description:
          "If you have a passion for creating exceptional and award-winning digital experiences with strong capabilities and talent in multiple languages and frameworks, we would love to hear from you.",
        id: "1",
      },
      {
        title: "React.js Developer",
        location: "Indianápolis",
        salary: 4000,
        description:
          "We are looking for a skilled React.js Developer to join our front-end development team. In this role, you will be responsible for developing and implementing user interface components using React.js concepts and workflows such as Redux, Flux, and Webpack.",
        id: "2",
      },
      {
        title: "Full Stack Engineer",
        location: "Las Vegas",
        salary: 3500,
        description:
          "We are looking for a skilled Full Stack Engineer to join our team. The ideal candidate is a talented professional with extensive technical expertise who can work alongside a small team and independently in the creation, maintenance, and updates of websites for Boxabl. Proficiency in JavaScript, HTML, CSS, and other web services and program applications is essential to succeeding in this role.",
        id: "3",
      },
      {
        title: "Front End Developer",
        location: "Wickliffe",
        salary: 2100,
        description:
          "We are looking for the right front end team to make it a reality. To take this project from being highly functional to highly functional AND extremely user friendly. We're on the forefront of coding technology and welcome new ideas and approaches. We need more than someone for grunt work - we need a team player who is looking to fully invest and make an impact. Sound interesting? We might just be looking for you!",
        id: "4",
      },
      {
        title: "Associate Front-End Developer",
        location: "New York",
        salary: 3200,
        description:
          "The Front-End Developer manages standalone applications for market initiatives which improve performance of the Nespresso US eCommerce responsive site. They will liaise with another front-end developer and the US market and Headquarters in Switzerland (peer-programming) for all technical eCommerce projects. Projects will be tied to Nespresso global roadmap, local initiatives, and daily operations. As an eCommerce Operations team member, they will report to Site Operations Manager and work in a growing team – four Content Producers and one Front End Developer.",
        id: "5",
      },
    ]);
    const order = ref<OrderTerm>("title");
    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };
    return { jobs, order, handleClick };
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title {
  display: flex;
  justify-content: center;
}
header img {
  width: 60px;
  margin-right: 20px;
}
header h1 {
  font-size: 3em;
}
</style>
