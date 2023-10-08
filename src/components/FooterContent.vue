<template>
   <div class="footer__content">
      <div class="footer__logo">
         <a :href="footerlogo[0].logoHref">
            <img :src="footerlogo[1].logoSrc" alt="Logo-icon" class="header__logo_img">
         </a>
         <p>{{ footerlogo[2].logoText }}</p>
         <div class="footer__socials">

            <img class="footer__icon footer__twitter" :src="footerlogo[3][0].footerSocialsSrc"
               :alt="footerlogo[3][0].footerSocialsAlt">
            <img class="footer__icon footer__linkedin" :src="footerlogo[3][1].footerSocialsSrc"
               :alt="footerlogo[3][1].footerSocialsAlt">
         </div>
      </div>
      <nav class="footer__nav">
         <h3 class="footer__subheader">{{ navdata[0].subheader }}</h3>
         <a v-for="(item, index) in navdata[1]" :key="index" :href="item.navHref" class="nav__item">{{ item.navValue }}</a>
      </nav>
      <div class="footer__contact">
         <h3 class="footer__subheader contact">{{ footercontact.subheader }}</h3>
         <p class="address">{{ footercontact.address }}</p>
         <p class="email">{{ footercontact.email }}</p>
         <p class="phone">{{ footercontact.phone }}</p>
      </div>
   </div>
</template>

<script>
export default {
   name: 'FooterContent',
   props: ['navdata', 'footercontact', 'footerlogo'],
   data() {
      return {

      }
   }

}
// <footer id="footer" class="footer">
//    <footer-content :navdata="navData" :footercontact="footerContact" :footerlogo="footerLogo"></footer-content>
// </footer>
</script>

<style lang="scss" scoped>
.footer {

   &__content {
      background-color: #ffffff;
      padding-bottom: 134px;
      margin: 0 auto;
      max-width: 1200px;
      display: flex;
      justify-content: space-between;
   }

   &__icon {
      width: 18px;
      height: 22px;
   }

   &__linkedin path:last-child {
      fill: red;
      stroke: blue;
   }

   &__logo img {
      margin-bottom: 18px;
   }

   &__logo p {
      color: #4D5053;
      font-size: 22px;
      line-height: 1.50;
      letter-spacing: 0.22px;
      max-width: 393px;
      margin-bottom: 31px;
   }

   &__socials {
      display: flex;
      gap: 54px;
   }

   &__nav {
      display: flex;
      flex-direction: column;
      margin-left: -300px;

      & .nav__item {
         color: #4D5053;
         font-size: 22px;
         line-height: 300%;
         letter-spacing: 0.22px;
      }
   }

   &__subheader {
      color: #292F36;
      font-family: 'DM Serif Display', serif;
      font-size: 25px;
      line-height: 1.25;
      margin-bottom: 10px;
   }

   &__contact {
      color: #4D5053;
      font-size: 22px;
      letter-spacing: 0.22px;
      max-width: 258px;
      // margin-left: -200px;
      margin-right: 15px;
   }
}

.contact {
   margin-bottom: 25px;
}

.address,
.email,
.phone {
   color: #4D5053;
   font-size: 22px;
   letter-spacing: 0.22px;
   margin-bottom: 15px;
}

.email,
.phone {
   line-height: 3.00;
}

.address {
   line-height: 1.50;
}
</style>