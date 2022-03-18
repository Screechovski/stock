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

export default {
  data() {
    return {
      stocks: [],
    };
  },
  components: {
    StockItem,
  },
  created() {
    companies.forEach((companyName, index) => {
      setTimeout(() => {
        axios.get(`https://financialmodelingprep.com/api/v3/profile/${companyName}?apikey=9a19f71b023140c8630b1f4111412cab`)
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
    @media screen and (max-width: 991px) {
        grid-template-columns: repeat(3, 1fr);
        gap: 15px;
    }
}
</style>
