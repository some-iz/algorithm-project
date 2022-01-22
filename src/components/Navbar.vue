<template>
  <b-navbar class="px-3 py-3" toggleable type="dark" variant="dark">
    <b-navbar-brand to="/">Algorithm Design Project</b-navbar-brand>
    <b-navbar-toggle target="navbar-toggle-collapse">
      <template #default="{ expanded }">
        <b-icon v-if="expanded" icon="chevron-bar-up"></b-icon>
        <b-icon v-else icon="chevron-bar-down"></b-icon>
      </template>
    </b-navbar-toggle>

    <b-collapse id="navbar-toggle-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-item to="/">Merge Sort Algorithm</b-nav-item>
        <b-nav-item to="/binary-search">Binary Search Algorithm</b-nav-item>
        <b-nav-item to="/source-code">All Source Code</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>
export default {

}
</script>

<style>

</style>