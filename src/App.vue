<template>
    <h2 class="title">My Stock App</h2>
    <StocksWrapper />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import StocksWrapper from './components/StocksWrapper.vue'

export default defineComponent({
    name: 'App',
    components: {
        StocksWrapper
    }
})
</script>

<style lang="scss">
:root {
    --textColor: #E4E4E4;
}
#app {
    padding: 50px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #0d0d0d;
    font-family: 'Baloo Tammudu 2', cursive;
    height: 100vh;
    width: 100vw;
    box-sizing: border-box;
    overflow: auto;
    scrollbar-width: none;
    &::-webkit-scrollbar {
        display: none;
    }

}
.title {
    font-size: 30px;
    color: #E4E4E4;
    text-transform: uppercase;
    margin-bottom: 1em;
}
</style>
