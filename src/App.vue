<template>
  <div>
    <div class="mobil-basket">
      <i class="fas fa-shopping-basket"></i>
    </div>
    <navbar></navbar>
    <home></home>
    <Footer></Footer>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Home from "@/components/Home.vue";
import Footer from "@/components/Footer.vue";

export default {
  components: {
    Navbar,
    Home,
    Footer,
  },
};
</script>
