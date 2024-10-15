<template>
  <TopNav />
  <router-view />
  <FooterBar />
</template>
<script>
import TopNav from "@/components/TopNav.vue";
import FooterBar from "@/components/FooterBar.vue";
export default {
  name: "App",
  components: {
    TopNav,
    FooterBar
  },
  computed: {
    // hide() {
    //   const hiddenPages = [
    //     'LoginPage', 'RegistrationPage', 'EmailVerificationPage', 'ForgotPasswordPage', 'ResetPasswordPage',  
    //   ]
    //   return hiddenPages.includes(this.$route.name)
    // }, 
  }
}
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

:root {
  --bg-primary: #237ABF;
  --bg-secondary: #283D90;
  --bg-third: #481E14;
}
</style>
