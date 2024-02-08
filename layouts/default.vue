<template>
  <div>
    <NavBar />
    <div id="app">

      <Head>
        <script>
          (function (w, d, s, l, i) {
            w[l] = w[l] || [];
            w[l].push({ "gtm.start": new Date().getTime(), event: "gtm.js" });
            var f = d.getElementsByTagName(s)[0],
              j = d.createElement(s),
              dl = l != "dataLayer" ? "&l=" + l : "";
            j.async = true;
            j.src = "https://www.googletagmanager.com/gtm.js?id=" + i + dl;
            f.parentNode.insertBefore(j, f);
          })(window, document, "script", "dataLayer", "GTM-KH7BJ6V");
        </script>
        <!-- Google Tag Manager (noscript) -->
        <noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-KH7BJ6V" height="0" width="0"
            style="display: none; visibility: hidden"></iframe></noscript>
        <!-- End Google Tag Manager (noscript) -->
      </Head>
      <Nuxt />

      <footer>
        <div class="col-lg-12 text-center">
              <u-btn
                to="/politica-de-cookies"
                label="Política de Cookies"
                flat
              />
              <u-btn
                to="/politica-de-privacidade"
                label="Política de Privacidade"
                flat
              />
            </div>
      </footer>
    </div>
  </div>
</template>
<style scoped>
#app {
  margin-top: 100px;
}
</style>
