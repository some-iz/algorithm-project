<template>
  <div>
    <navbar></navbar>
    <div class="vh-100 w-100 bg-dark d-flex flex-column justify-content-center align-items-center">
      <a class="text-light" href="https://github.com/some-iz/algorithm-project">
        جهت نمایش سورس  آپلود شده در گیت هاب  اینجا کلیک نمایید...
      </a>
      <img class="img-fluid h-100" src="../assets/carbon.png">
    </div>
  </div>
</template>

<script>
import Navbar from '../components/Navbar.vue'
export default {
  components: { Navbar },
}
</script>

<style>
a{
  font-family: 'iransans';
  text-decoration: none;
  direction: rtl;
  font-weight: 500;
}
</style>