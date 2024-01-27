<template>
  <b-container class="page  animate__animated animate__fadeIn">
    <h2>My certifications</h2>
    <b-row class="articles" v-if="blogs.length > 0">
      <div class="col-md-6" v-for="blog in blogs" :key="blog.id">
        <div>
          <b-card-group deck>
            <b-card
              :img-src="blog.image"
              img-top
              tag="article"
              class="mb-2"
            >
              <h4>{{ blog.title }}</h4>
              <hr />

              <b-button
                :href="blog.image"
                target="_blank"
                rel="noopener"
                variant="default"
                >Expand..</b-button
              >
            </b-card>
          </b-card-group>
        </div>
      </div>
    </b-row>
  </b-container>
</template>
<script>
import HeartIcon from "vue-ionicons/dist/md-heart.vue";
export default {
  components: { HeartIcon },
  data() {
    return {
      showLoader: true,
      showErrALert: false,
      tagVariants: ["primary", "success", "warning", "info", "dark", "danger"],
      blogs: []
    };
  },
  head: {
    title: "My certifications 📚 - Eder Antonio",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "certifications: web development (html, css, javascript), mobile app development and many more."
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "My my certifications 📚 - Eder Antonio"
      },
      {
        property: "og:description",
        content: "certifications: web development (html, css, javascript), mobile app development and many more."
      },
    ]
  },
  methods: {
    // get articles hosted on dev.to
    getCourses() {
      this.blogs = [
        {
          id: Math.random() * 1000,
          title: "Vue3: Vuex 4, Typescript, Mixins e Hooks",
          image:  require("@/assets/courses/alura-vue-3-avancado.png"),
        },
        {
          id: Math.random() * 1000,
          title: "SEO PARA E-COMMERCE: ESTRATÉGIAS PARA ALCANÇAR UM BOM POSICIONAMENTO NOS SITES DE BUSCA",
          image:  require("@/assets/courses/seo-alura.png"),
        },
        {
          id: Math.random() * 1000,
          title: "React It covers topics like Basic Routing, Rendering Elements,State Management (Internal Component State), Handling Events, ES6 and JavaScript",
          image:  require("@/assets/courses/react_basic_certificate.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Web3 SMART CONTRACT + BLOCKCHAIN + JAVASCRIPT + SOLIDITY LANG",
          image:  require("@/assets/courses/web3.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Curso de SEO Completo - Do básico ao avançado",
          image:  require("@/assets/courses/24.jpeg"),
        },
        {
          id: Math.random() * 1000,
          title: "React Completo do básico ao avançado ",
          image:  require("@/assets/courses/23.jpeg"),
        },
        {
          id: Math.random() * 1000,
          title: "Google Firebase na Prática com JavaScript",
          image:  require("@/assets/courses/22.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "MicroFrontend com SingleSPA",
          image:  require("@/assets/courses/21.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "ES6/7 / Webpack 2 / TypeScript",
          image:  require("@/assets/courses/ts-01.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Vuejs 3, Vuex e Vue Router",
          image:  require("@/assets/courses/1.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Analytics para iniciantes",
          image:  require("@/assets/courses/2.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Scrum",
          image:  require("@/assets/courses/3.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Vuejs 2",
          image:  require("@/assets/courses/4.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Vuejs com PWA",
          image:  require("@/assets/courses/5.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Docker",
          image:  require("@/assets/courses/6.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Levantamento de requisitos",
          image:  require("@/assets/courses/7.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Liderança",
          image:  require("@/assets/courses/8.png"),
        },
        {
          id: Math.random() * 1000,
          title: "HTML5 Web Storage",
          image:  require("@/assets/courses/9.png"),
        },
        {
          id: Math.random() * 1000,
          title: "HTML Básico",
          image:  require("@/assets/courses/10.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "CSS/Sass",
          image:  require("@/assets/courses/11.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Vuejs 01",
          image:  require("@/assets/courses/12.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Vuejs 02",
          image:  require("@/assets/courses/13.jpg"),
        },
        {
          id: Math.random() * 1000,
          title: "Fundamentos do JavaScript",
          image:  require("@/assets/courses/14.png"),
        },
        {
          id: Math.random() * 1000,
          title: "Introdução ao JavaScript",
          image:  require("@/assets/courses/15.png"),
        },
        {
          id: Math.random() * 1000,
          title: 'O que é .NET',
          image: require('@/assets/courses/16.png')
        },
        {
          id: Math.random() * 1000,
          title: 'O que é NPM',
          image: require('@/assets/courses/17.png')
        },
        {
          id: Math.random() * 1000,
          title: 'O que é Vuejs',
          image: require('@/assets/courses/18.png')
        },
        {
          id: Math.random() * 1000,
          title: 'O que é PHP',
          image: require('@/assets/courses/19.png')
        },
        {
          id: Math.random() * 1000,
          title: 'PHP iniciantes',
          image: require('@/assets/courses/20.png')
        }
      ]
    }
  },
  mounted() {
    this.getCourses();
  }
};
</script>
<style scoped>
img {
  height: auto !important;
}
.container {
  margin-top: 120px;
}
.row {
  margin-top: 40px;
}
.spinner-border {
  margin-top: 40px;
}
.card {
  text-align: left;
  color: #000;
}
</style>
