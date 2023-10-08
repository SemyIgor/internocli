<template>
   <header id="header" class="header">
      <div class="header__content center">
         <div class="header__logo">
            <a href="./index.html">
               <img src="../assets/img/home/logo.svg" alt="Logo-icon" class="header__logo_img">
            </a>
         </div>
         <nav class="header__nav">
            <a v-for="(item, index) in navData" :key="index" :href="item.navHref" class="nav__item">
               {{ item.navValue }}
            </a>
         </nav>
      </div>
   </header>
</template>

<script>
export default {
   name: 'HeaderContent',
   props: {
      navData: Array,
   },
   data() {
      return {
      };
   },
   computed: {}
}
</script>

<style lang="scss" scoped>
@import "@/assets/scss/variables";
@import "@/assets/scss/extends";

.header {
   background-color: #ffffff;
   margin: 0 auto;
   padding-top: 44px;
   padding-bottom: 57px;
   position: relative;

   // width: 1200px;
   &__content {
      max-width: 1200px;
      @extend %flexRowBetween !optional;
   }

   &__logo {
      @extend %flexRowBetween !optional;
      gap: 41px;

      & img {
         cursor: pointer;
      }
   }

   &__nav {
      display: flex;
      justify-content: space-between;
      gap: 50px;
   }

   // &__burger {
   //    margin-bottom: -17px;
   // }
}

.nav__item {
   color: #292F36;
   font-size: 2rem;
}

.project-face {
   height: 356px;
   width: 100%;
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: flex-end;
   background-color: #F4F0EC;
   background-image: url('../assets/img/project/project-face.png');
   background-size: cover;
   background-position: center;

   &__content {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      margin: 0 auto;
      max-width: 1200px;
   }

   &__tab {
      display: flex;
      max-width: 503px;
      padding: 41px 125px;
      flex-direction: column;
      align-items: center;
      gap: 10px;
      border-radius: 37px 37px 0px 0px;
      background: #FFF;
   }

   &__title {
      text-align: center;
      color: #292F36;
      font-family: 'DM Serif Display', serif;
      font-size: 50px;
      line-height: 1.25;
      font-weight: 400;
   }

   &__anchor {
      text-align: center;
      color: #4D5053;
      font-size: 22px;
      line-height: 1.50;
      letter-spacing: 0.22px;
   }
}

.categories {
   display: flex;
   justify-content: space-around;
   align-items: center;
   max-width: 880px;
   margin: 0 auto;
   margin-top: 200px;
   border-radius: 18px;
   border: 1px solid #CDA274;

   &__item {
      color: #292F36;
      font-size: 18px;
      font-weight: 600;
      line-height: 1.25;
      letter-spacing: 0.36px;
      padding-top: 26px;
      padding-bottom: 26px;
      border-radius: 18px;
      flex-grow: 1;
      text-align: center;
      cursor: pointer;

      &_active {
         background: #CDA274;

         color: #FFF;
         font-weight: 500;
      }
   }
}

.cards-module {
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
      /* display: grid; */
      /* grid-template-columns: repeat(auto-fit, minmax(550px, 1fr)); */
      columns: 2;

      break-inside: avoid;
      gap: 30px;
      margin-bottom: 61px;

   }

   &__card {
      /* grid-column: span 1; */
      /* justify-self: center; */
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
      /* font-family: Jost; */
      font-size: 22px;
      line-height: 1.5;
      letter-spacing: 0.22px;
   }


   &__arrow {
      width: 70px;
      cursor: pointer;
   }
}
</style>