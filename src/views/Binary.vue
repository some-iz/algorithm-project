<template>
    <div class="home bg-dark">
        <navbar></navbar>
        <container></container>
    </div>
</template>

<script>
import Container from '../components/Container.vue';
import Navbar from '../components/Navbar.vue'
export default {
    name: 'Home',
    components: {
        Navbar,
        Container,
    },
}
</script>
<style scoped>
    .home {
        display: flex;
        flex-direction: column;
        min-height: 100%;
    }
</style>