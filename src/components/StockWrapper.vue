<template>
    <div class="stock">
        <StockItem
            v-for="stock, index in stocks"
            :key="index"
            :title="stock.companyName"
            :abbr="stock.symbol"
            :price="stock.price"
            :imageUrl="stock.image"
        />
    </div>
</template>

<script>
import axios from 'axios';
import StockItem from '@/components/StockItem.vue';
import companies from '@/assets/companies';

const apiKey = '1c15180172c4cc4f4ab4e0e5407fec7b';

export default {
    data: () => ({
        stocks: [],
    }),
    components: {
        StockItem,
    },
    created() {
        companies.forEach((companyName, index) => {
        setTimeout(() => {
            axios.get(`https://financialmodelingprep.com/api/v3/profile/${companyName}?apikey=${apiKey}`)
                .then((response) => {
                    console.log(response.data);
                    this.stocks = [...this.stocks, ...response.data];
                })
                .catch(console.warn);
        }, 1000 * (index + 1));
        });
    },
};
</script>

<style lang="scss">
    .stock {
        width: 100%;
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
        margin: 20px 0px;
        @media screen and (max-width: 1367px) {
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
        }
    }
</style>
