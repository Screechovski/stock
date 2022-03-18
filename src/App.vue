<template>
    <StockWrapper />
</template>

<script>
import StockWrapper from '@/components/StockWrapper.vue';

export default {
  name: 'App',
  components: {
    StockWrapper,
  },
};
</script>

<style lang="scss">
:root {
    --textColor: #E4E4E4;
}
body {
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
