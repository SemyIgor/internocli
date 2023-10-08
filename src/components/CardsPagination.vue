<template>
   <div v-show="numberOf > 1" class="cards__pagination">

      <div v-show="numFirstVisible > 1" @click="$emit('pagiLeft')" class="cards__pagiArrow">
         <svg xmlns="http://www.w3.org/2000/svg" width="53" height="52" viewBox="0 0 53 52" fill="none">
            <circle cx="26.5" cy="26" r="25.5" stroke="#CDA274" />
            <path d="M29.5 32L23.5571 25.3143L29.5 18.6286" stroke="#292F36" stroke-width="2" stroke-linecap="round"
               stroke-linejoin="round" />
         </svg>
      </div>

      <div @click="pagiChoiceModule(n)" v-for="(n, index) in numberOf" :key="index"
         v-show="n >= numFirstVisible && n < numFirstVisible + 3" class="cards__pagiNumber">0{{ n }}
      </div>

      <div v-show="(numFirstVisible + 2) < numberOf" @click="$emit('pagiRight')" class="cards__pagiArrow">
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
      // Общее количество точек пагинации, переданное от родителя
      numberOf: Number,
      // Номер самой левой, из видимых, ячейки пагинации
      numFirstVisible: Number,
   },
   computed: {

   },
   methods: {
      pagiChoiceModule(num) {
         this.$emit('pagiChoice', num);
         console.log('num: ', num);

      },
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
      align-items: center;
   }

   &__pagiNumber,
   &__pagiArrow {
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

   &__pagiNumber {
      border: 1px solid #CDA274;
   }

   &__pagiNumber:hover {
      border: 1px solid #F4F0EC;
   }

   &__pagiNumber_active {
      border: 1px solid #F4F0EC;
      background-color: #F4F0EC;
   }

   &__pagiArrow:hover circle {
      stroke: #F4F0EC;
   }
}
</style>