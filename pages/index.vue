<template>
  <div>
    <b-row style="margin-left: 0; margin-right: 0">
      <b-col md="4">
        <b-img :src="avatar" id="avatar-img" alt="Asaolu Elijah Memoji" />
        <!-- @mouseenter="changeAvatar"
        @mouseleave="changeAvatar" -->
      </b-col>

      <b-col md="8">
        <h2 class="intro animate__animated animate__fadeInUp animate__fast">
          Hi 👋,
          <br />I<span>'m Eder Antonio</span>.
        </h2>

        <div class="col-md-10 info">
          A <b>Full Stack developer</b> and <b>technical writer</b> passionate
          about solving problems with tech.<br />
          I am skilled with building exceptional <b>websites</b> and
          <b>mobile applications</b>.
          <br />
          <b-button
            class="action-btn animate__animated animate__wobble animate__delay-4s animate__fast"
            to="/projects"
          >
            Explore >
          </b-button>

          <b-button class="action-btn" @click="openChat()" variant="primary">
            Get In Touch
          </b-button>

          <!-- .SOCIAL LINKS SECTION -->
          <div
            class="social-icons animate__animated animate__fadeInUp animate__delay-1s"
          >
            <social-link :to="socialLinks.github">
              <GithubIcon />
            </social-link>

            <social-link :to="socialLinks.linkedin">
              <LinkedinIcon />
            </social-link>

            <social-link :to="socialLinks.facebook">
              <FacebookIcon />
            </social-link>

            <social-link :to="socialLinks.mail">
              <MailIcon />
            </social-link>

            <social-link :to="socialLinks.youtube">
              <YoutubeIcon />
            </social-link>
          </div>
        </div>
      </b-col>
    </b-row>
    <div class="freelancer">
      <social-link :to="socialLinks.freelancer">
        <div class="freelancer__looking">
          <h4>Está buscando um desenvolvedor?</h4>
          <h5>Are you looking for a developer?</h5>
        </div>
        <img class="freelancer__img" src="../assets/eder-freelancer.png" />
      </social-link>
    </div>
    <AlertCookies />
  </div>
</template>

<script>
import GithubIcon from "vue-ionicons/dist/logo-github.vue";
import LinkedinIcon from "vue-ionicons/dist/logo-linkedin.vue";
import FacebookIcon from "vue-ionicons/dist/logo-facebook.vue";
import YoutubeIcon from "vue-ionicons/dist/logo-youtube.vue";
import MailIcon from "vue-ionicons/dist/md-mail.vue";
import AlertCookies from '../components/AlertCookies.vue';

export default {
  components: {
    GithubIcon,
    LinkedinIcon,
    FacebookIcon,
    YoutubeIcon,
    MailIcon,
    AlertCookies
  },

  data() {
    return {
      avatar:
        "https://uploaddeimagens.com.br/images/004/524/882/full/profile-pic.png?1688000153", // require("@/assets/avatar-1.webp"),
      // ADD YOUR SOCIAL LINKS HERE 👇
      socialLinks: {
        freelancer: "https://freelancer.ederantonio.com.br/",
        github: "https://github.com/antonioEDER",
        linkedin: "https://www.linkedin.com/in/eder-antonio-3b7021122/",
        facebook: "https://www.facebook.com/Ederantonio1993/",
        mail: "mailto:antonioeder007@gmail.com",
        youtube: "https://www.youtube.com/channel/UCC5uHA2n_9wmQpBFPQVn_Pg",
      },
    };
  },

  head: {
    title: "Portfolio ⚡ - Eder Antonio Programador",
    meta: [
      {
        hid: "description",
        name: "description",
        content:
          "Eder Antonio - Graduado em Sistemas de Informação -Programador Full Stack",
      },
      {
        hid: "og:title",
        name: "og:title",
        content: "Portfolio ⚡ - Eder Antonio",
      },
      {
        property: "og:description",
        content:
          "Eder Antonio - Graduado em Sistemas de Informação -Programador Full Stack",
      },
      {
        hid: "og:image",
        name: "og:image",
        content: require("@/assets/coding.png"),
      },
    ],
  },
  methods: {
    changeAvatar() {
      if (this.avatar == require("@/assets/avatar-2.webp")) {
        this.avatar = require("@/assets/avatar-1.webp");
      } else {
        this.avatar = require("@/assets/avatar-2.webp");
      }
    },
    openChat() {
      jivo_api.open();
    },
  },
  mounted() {
    this.$nextTick(() => {
      this.$nuxt.$loading.start();

      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });
  },
};
</script>

<style>
.freelancer>a{
  color: #280a5c;
}
.freelancer {
  color: white;
  margin-top: 30px;
  margin-bottom: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.freelancer__img {
  margin-top: 20px;
  background-color: rgb(46, 42, 42);
  border-radius: 10px;
  max-width: 450px;
  width: 100%;
  height: auto;
  cursor: pointer;
}
.freelancer__looking {
  width: 100%;
  max-width: 450px;
  background-color: white;
  padding: 10px;
  border-radius: 10px;
  box-shadow: transparent;
  box-shadow: 5px 10px #888888;
}
</style>
