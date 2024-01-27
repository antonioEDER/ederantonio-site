<template>
  <div class="container animate__animated animate__fadeIn">
    <div class="row">
      <div class="col-md-6">
        <div class="about">
          <h1 class="line-after">About Me</h1>
          <h4 class="mt-4">Hey 👋</h4>
          <p>
            My name is Eder Antonio, I am a <b>Full Stack  developer</b> and
            <b>technical writer</b>.
          </p>
          <p>
            I have <b>{{ currYear - startYear }}+ years experience</b> in
            develop web and mobile applications. Plus I am an agile
            learner, I learn new cool stuffs everyday.
          </p>
          <h4 class="mt-5">Tech Stacks</h4>
          <p>Below are some of the technologies I use daily:</p>
          <div class="row animate__animated animate__fadeInUp">
            <div class="col">
              <ul style="list-style-type: circle;">
                <li>HTML & CSS</li>
                <li>Node.js</li>
                <li>PHP</li>
                <li>GOLANG</li>
                <li>MYSQL</li>
                <li>PostGress</li>
              </ul>
            </div>
            <div class="col">
              <ul style="list-style-type: circle;">
                <li>JavaScript</li>
                <li>Vue.js</li>
                <li>ReactJs</li>
                <li>SCSS</li>
                <li>CapacitorJs</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <img
          src="@/assets/working.png"
          alt="About Illustration"
          class="abt-img"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      startYear: 2016,
      currYear: new Date().getFullYear(),
      stacks: [
        {
          language: "HTML",
          experience: "3+ Years",
          variant: "secondary",
          breif: "lorem..."
        },
        {
          language: "CSS",
          experience: "3+ Years",
          variant: "primary",
          breif: "lorem..."
        },
        {
          language: "Javascript",
          experience: "2+ Years",
          variant: "warning",
          breif: "lorem..."
        },
        {
          language: "VUE.JS",
          experience: "2+ Years",
          variant: "success",
          breif: "lorem..."
        },
        {
          language: "Node.js",
          experience: "2+ Years",
          variant: "dark",
          breif: "lorem..."
        }
      ]
    };
  },
  head: {
    title: "About 🕵️‍♂️ - Eder Antonio",
    meta: [
      {
        hid: "description",
        name: "description",
        // currYear - startYear
        content: "Eder Antonio - Graduado em Sistemas de Informação - Programador Full Stack"
      }
    ]
  }
};
</script>
<style scoped>
.row {
    margin-top: 30px;
}
.container {
  margin-top: 140px;
  text-align: left;
}
.line-after {
  overflow: hidden;
}
.line-after::after {
  content: "";
  display: inline-block;
  height: 0.5em;
  vertical-align: bottom;
  width: 100%;
  margin-right: -100%;
  margin-left: 10px;
  border-top: 2px solid rgb(211, 46, 46);
}
.abt-img {
  width: inherit;
  height: inherit;
  border-radius: 5px;
}
/* .abt-img:hover {
  animation: swing;
  animation-duration: 2s;
} */
</style>
