<template>
   <section id="cards-module__content" class="cards-module">

      <!-- Вывод табов -->
      <CategoriesModule :categories="tagsArray" @activate-it="chooseTag" />

      <!-- Показывает количество блоков из 8 фото (убрать после отладки) -->
      <h2>{{ pagiNumbersLength }}</h2>

      <div class="cards-module__content">

         <!-- Вывод карточек -->
         <div class="cards-module__cards">
            <div v-for="(card, index) in paginatedCards" :key="index" class="cards-module__card">
               <!-- <div v-for="(card, index) in filteredCards" :key="index" class="cards-module__card"> -->
               <img :src="card.cardImagePath" alt="cardImageAlt" class="cards-module__image cards-module__image1">
               <div class="cards-module__info">

                  <div class="cards-module__text">
                     <div class="cards-module__header" v-html="card.cardHeader">
                     </div>

                     <div class="cards-module__subtext"> {{ card.cardSubtext }}
                     </div>
                  </div>

                  <div class="cards-module__arrow">
                     <a href="./blog-details.html">
                        <svg viewBox="0 0 70 70" fill="none" xmlns="http://www.w3.org/2000/svg">
                           <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                           <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                              stroke-linejoin="round" />
                        </svg>
                     </a>
                  </div>

               </div>
            </div>
         </div>

         <CardsPagination :numberOf="pagiNumbersLength" @pagiChoice="choosePagination" />

      </div>
   </section>
</template>

<script>
import CategoriesModule from './CategoriesModule.vue';
import CardsPagination from './CardsPagination.vue';

export default {
   name: 'CardsModuleCard',
   components: {
      CategoriesModule,
      CardsPagination
   },
   props: ['cards'],
   data() {
      return {
         tagsArray: [
            { id: 1, name: 'Bathroom', activated: '' },
            { id: 2, name: 'Bed Room', activated: '' },
            { id: 3, name: 'Kitchen', activated: '' },
            { id: 4, name: 'Living Area', activated: '' },
         ],
         tagsIndex: 0,
         filteredCardsNumber: 0, // Номер нажатого таба (0 - нет нажатого)
         chosenPagination: 1,
      };
   },
   computed: {
      // Фильтруем карточки согласно выбранному табу
      filteredCards() {
         let arr = [];
         if (!this.tagsIndex) {
            arr = this.cards;
         } else {
            arr = this.cards.filter(
               (card) => card.category == this.tagsArray[this.tagsIndex - 1].name
            );
         }
         return arr;
      },
      pagiNumbersLength() {
         return Math.ceil(this.filteredCards.length / 8);
      },
      paginatedCards() {
         let arr = [];
         if (!this.chosenPagination) {
            arr = this.filteredCards;
         } else {
            arr = this.filteredCards.slice((this.chosenPagination - 1) * 8, this.chosenPagination * 8);
         }
         return arr;
      },

      // Клонируем массив табов для того, чтобы не менять исходный массив при присвоении свойства =active=
      // cloneTagsArray() {
      //    const arr = Object.assign([], this.tagsArray);
      //    return arr;
      // },
   },
   methods: {
      chooseTag(id) {
         // console.log('id: ', id);
         // Обнуляем пагинацию
         this.chosenPagination = 1;

         // Обнуляем активность кнопок выбора табов
         this.tagsArray.forEach((element) => {
            // console.log(element.activated, this.tagsIndex);
            element.activated = '';
         });
         // Если нажали на уже выбранный таб
         if (this.tagsIndex == id) {
            this.tagsIndex = 0;
            // Если нажали на невыбранный таб
         } else {
            this.tagsIndex = id;
            this.tagsArray[id - 1].activated = 'categories__item_active';
         }
      },
      choosePagination(pagiNum) {
         // console.log('pagiNum: ', pagiNum);
         // return pagiNum;
         this.chosenPagination = pagiNum;

      }
   }

}
</script>

<style lang="scss" scoped>
.cards {
   &-module {
      background-color: #ffffff;
      padding-top: 200px;

      &__content {
         padding-top: 96px;
         padding-bottom: 96px;
         margin: 0 auto;
         position: relative;
         max-width: 1200px;
      }

      &__cards {
         // display: grid;
         // grid-template-columns: repeat(auto-fit, minmax(550px, 1fr));
         columns: 2;

         break-inside: avoid;
         gap: 30px;
         margin-bottom: 61px;

      }

      &__card {
         // grid-column: span 1;
         // justify-self: center;
         width: 100%;
         display: flex;
         flex-direction: column;
         break-inside: avoid;
         margin-bottom: 35px;

      }

      &__image {
         width: 100%;
         margin-bottom: 28px;
      }

      &__info {
         display: flex;
         justify-content: space-between;
      }

      &__header {
         color: #292F36;
         font-family: 'DM Serif Display', serif;
         font-size: 25px;
         letter-spacing: 0.5px;
         margin-bottom: 4px;
      }

      &__subtext {
         color: #4D5053;
         // font-family: Jost;
         font-size: 22px;
         line-height: 1.5;
         letter-spacing: 0.22px;
      }


      &__arrow {
         width: 70px;
         cursor: pointer;
      }
   }
}
</style>
