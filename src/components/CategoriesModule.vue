<template>
   <div class="categories">
      <div v-for="category in categories" :key="category.id" class="categories__item"
         @click="$emit('activate-it', category.id)" :class="category.activated">{{ category.name }}</div>
   </div>
</template>

<script>
export default {
   name: 'CategoriesModule',
   props: ['categories'],
   data() {
      return {
         index: 0,
      };
   },
   computed: {},
   methods: {},

}
</script>

<style lang="scss" scoped>
.categories {
   display: flex;
   justify-content: space-around;
   align-items: center;
   max-width: 880px;
   margin: 0 auto;
   // margin-top: 200px;
   border-radius: 18px;
   border: 1px solid #CDA274;

   &__item {
      color: #292F36;
      font-size: 18px;
      font-weight: 600;
      line-height: 1.25;
      letter-spacing: 0.36px;
      // padding: 26px 66px;
      padding-top: 26px;
      padding-bottom: 26px;
      // border: red 1px solid;
      border-radius: 18px;
      flex-grow: 1;
      text-align: center;
      cursor: pointer;

      &_active {
         background: #CDA274;

         color: #FFF;
         // font-size: 18px;
         font-weight: 500;
         // line-height: 125%;
         // letter-spacing: 0.36px;
      }
   }
}
</style>