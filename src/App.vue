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
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #212121;
    font-family: 'Baloo Tammudu 2', cursive;
    height: 100vh;
    width: 100vw;
    box-sizing: border-box;
    overflow: auto;
    scrollbar-width: none;
    padding: 0px 20px;
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
