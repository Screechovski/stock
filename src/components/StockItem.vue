<template>
    <div class="stock-item">
        <div class="stock-item__image">
            <img :src="imageUrl" alt="">
        </div>
        <div class="stock-item__info">
            <h3 class="stock-item__title">{{title}}</h3>
            <p class="stock-item__abbr">{{abbr}}</p>
        </div>
        <span class="stock-item__price">{{price}} $</span>
    </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    price: {
      type: Number,
      required: true,
    },
    abbr: {
      type: String,
      required: true,
    },
    imageUrl: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="sass">
.stock-item
    background-color: #000000
    border-radius: 20px
    padding: 10px
    display: flex
    align-items: center
    box-shadow: 0px 0px 10px 0px #7e7e7e1a
    gap: 10px
    &__info
    &__title
        color: var(--textColor)
        font-size: 14px
        margin-bottom: 0.5em
        margin-top: 0
    &__abbr
        color: #787878
        font-size: 14px
        text-transform: uppercase
        margin-bottom: 0
    &__image
        height: 50px
        width: 50px
        min-height: 50px
        min-width: 50px
        background-color: #ffffff
        border-radius: 10px
        overflow: hidden
        img
            max-height: 100%
            max-width: 100%
            height: 100%
            width: 100%
            object-fit: contain
    &__price
        text-transform: uppercase
        color: var(--textColor)
        margin-left: auto
        font-size: 15px
        white-space: nowrap
</style>
