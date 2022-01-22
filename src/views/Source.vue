<template>
  <div>
    <navbar></navbar>
    <div class="w-100 bg-dark d-flex flex-column justify-content-center align-items-center">
      <a class="text-light mt-3" href="https://github.com/some-iz/algorithm-project">
        جهت نمایش سورس  آپلود شده در گیت هاب  اینجا کلیک نمایید...
      </a>

      <hr>
      <h2 class="mt-2">
          Merge Sort Algorithm
      </h2>
      <img class="img-fluid h-100" src="../assets/merge.png">
      <img class="img-fluid h-100" src="../assets/merge-sort.png">

      <h2 class="mt-5">
          Binary Search Algorithm
      </h2>
      <img class="img-fluid h-100" src="../assets/bin.png">

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
h2{
  color: white;
  cursor: default;
}
</style>