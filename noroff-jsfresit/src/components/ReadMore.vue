<template>

    <div class="read-more__item-container">
      <div class="read-more__item" v-for="(value, key) in cardinfo" v-bind:key="key">
        <div class="read-more__item-key">{{key}}</div>
        <div class="read-more__item-value">{{value}}</div>
      </div>
    </div>

</template>

<script>
export default {
    name: 'ReadMore',
    props: ['cardinfo']
};
</script>

<style lang="stylus" scoped>

.read-more

    &__item-container
        padding 20px
        padding-left 0

    &__item
        display flex
        justify-content space-between

        font-weight: normal;
        font-size: 1.2em;
        line-height: 21px;
        letter-spacing: 0.045em;

        color: #2F2F2F;
        text-transform: capitalize;

        // margin-top 0.3em
        padding 10px 10px

    &__item:nth-child(odd)
        background #F6D301

    &__item-key
       font-weight bold 

</style>