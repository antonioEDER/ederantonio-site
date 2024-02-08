<template>
  <div>
    <BModal v-model="dialog" hide-header hide-footer class="modal-bottom" size="lg">
      <BCard style="width: 100%"  class="alert-cookier">
        <div class="items-center">
          <div>
            <div class="text-weight-bold alert-cookier__title">Sobre o uso de cookies</div>
            <div>
              Nós usamos cookies e outras tecnologias semelhantes para melhorar
              a sua experiência em nossos serviços, personalizar publicidade e
              recomendar conteúdo de seu interesse. Ao utilizar nossos serviços,
              você está ciente dessa funcionalidade. Conheça nosso
              <a href="https://freelancer.ederantonio.com.br/politica-de-cookies">Política de Cookies</a> e consulte
              nossa
              <a href="https://freelancer.ederantonio.com.br/politica-de-privacidade">Política de Privacidade</a>.
            </div>
          </div>
          <div class="text-right alert-cookier__btn">
            <b-button @click="aceitarCookies">Prosseguir</b-button>
          </div>
        </div>
      </BCard>
    </BModal>
  </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent({
  name: 'AlertCookies',
  data() {
    return {
      dialog: false,
    };
  },
  mounted() {
    const aceite = localStorage.getItem('aceite_cookie');
    if (!aceite) {
      this.dialog = true;
    }
  },
  methods: {
    aceitarCookies() {
      this.dialog = false;
      localStorage.setItem('aceite_cookie', 'true');
    },
  },
});
</script>

<style>
.alert-cookier {
  color: grey;
}
.alert-cookier__btn {
  margin-top: 20px;
}
.alert-cookier__title {
  font-weight: bold;
}
.modal.show .modal-dialog {
  width: 100% !important;
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  margin: 0 auto;
}
</style>