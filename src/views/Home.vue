<template>
  <div class="home bg-dark">
    <Navbar></Navbar>
    <Container></Container>
  </div>
</template>

<script>
import Container from '../components/Container2'
import Navbar from '../components/Navbar'
export default {
  name: 'Home',
  components: {
    Navbar,
    Container,
  },
  }
</script>
<style>
.home{
  display: flex;
  flex-direction: column;
  min-height: 100%;
}
html{
  scrollbar-width: thin;
}
</style>