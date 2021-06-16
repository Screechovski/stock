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
import StockItem from './StockItem.vue';
import axios from 'axios';
export default {
    data(){
        return {
            stocks: []
        }
    },
    components: {
        StockItem
    },
    created(){
        // const apiResponce = await axios.get('https://financialmodelingprep.com/api/v3/profile/AAPL,NVDA,TSLA,AMD,INTC,MDB,SPCE,V,DAL,DOCU,OKTA,AMZN,PINS,TRIP,GDDY,DIS,MCD,NOK,UPWK,IBM,FB,ZM,OZON,NFLX,EA,HLT,H,CCL?apikey=6c9be8fcb7df7894ba5ae48be14935fc');
        axios.get('https://financialmodelingprep.com/api/v3/profile/AAPL,NVDA,TSLA,AMD,INTC,MDB,SPCE,V,DAL,DOCU,OKTA,AMZN,PINS,TRIP,GDDY,DIS,MCD,NOK,UPWK,IBM,FB,ZM,OZON,NFLX,EA,HLT,H,CCL?apikey=0a63e6339c468c8bb8596525bfb5fbe3')
            .then(response => {
                console.log(response.data);
                return response;
            })
            .then(({data})=>this.stocks = data)
    }
}
</script>

<style lang="scss">
.stock {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    @media screen and (max-width: 991px) {
        grid-template-columns: repeat(3, 1fr);
        gap: 15px;
    }
}
</style>