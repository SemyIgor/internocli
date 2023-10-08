<template>
   <div v-show="numberOf > 1" class="cards__pagination">
      <div @click="pagiChoiceModule(n)" v-for="n in numberOf" :key="n" class="cards__pagiNumber">0{{ n }}</div>
      <!-- <div @click="$emit('pagiChoice', n)" v-for="n in numberOf" :key="n" class="cards__pagiNumber">0{{ n }}</div> -->

      <div class="cards__pagiNumber">
         <svg xmlns="http://www.w3.org/2000/svg" width="53" height="52" viewBox="0 0 53 52" fill="none">
            <circle cx="26.5" cy="26" r="25.5" stroke="#CDA274" />
            <path d="M23.5571 32L29.5 25.3143L23.5571 18.6286" stroke="#292F36" stroke-width="2" stroke-linecap="round"
               stroke-linejoin="round" />
         </svg>
      </div>
   </div>
</template>

<script>
export default {
   name: 'CardsPagination',
   props: {
      numberOf: Number,
   },
   methods: {
      pagiChoiceModule(num) {
         this.$emit('pagiChoice', num);
      }
   }

}
</script>
<style lang="scss" scoped>
.cards {
   &__pagination {
      // max-width: 268px;
      margin: 0 auto;
      margin-top: 61px;
      display: flex;
      justify-content: center;
      gap: 20px;
      // justify-content: space-between;
      align-items: center;
   }

   &__pagiNumber {
      box-sizing: border-box;
      width: 52px;
      height: 52px;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      color: #292F36;
      font-size: 16px;
      font-weight: 500;
      line-height: 1.50;
      cursor: pointer;

      &:hover {
         background-color: #F4F0EC;
      }
   }

   &__pagiNumber:not(:last-child) {
      border: 1px solid #CDA274;
   }

   &__pagiNumber:not(:last-child):hover {
      border: 1px solid #F4F0EC;
   }

   &__pagiNumber:last-child:hover circle {
      stroke: #F4F0EC;
   }
}
</style>