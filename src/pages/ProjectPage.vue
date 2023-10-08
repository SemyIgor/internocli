<template>
   <div id="project" class="project">
      <HeaderContent :navData="navData" />
      <ProjectFaceContent :projfacetab="projFaceTab" />
      <CardsModuleCard :cards="impCards.cards" />
      <FooterContent :navdata="navData" :footercontact="footerContact" :footerlogo="footerLogo" />
   </div>
</template>

<script>
import HeaderContent from '../components/HeaderContent.vue';
import ProjectFaceContent from '../components/ProjectFaceContent.vue';
import CardsModuleCard from '../components/CardsModuleCard.vue';
import FooterContent from '../components/FooterContent.vue';
import impCards from '../assets/json/project_card.json';

export default {
   name: 'ProjectPage',
   components: {
      HeaderContent,
      ProjectFaceContent,
      CardsModuleCard,
      FooterContent
   },
   data() {
      return {
         navData: [
            { subheader: 'Pages' },
            [
               { navHref: './index.html', navValue: 'Home' },
               { navHref: './project.html', navValue: 'Project' },
               { navHref: './blog.html', navValue: 'Blog' },
            ],
         ],
         footerContact: {
            subheader: 'Contact',
            address: '55 East Birchwood Ave. Brooklyn, New York 11201',
            email: 'contact@interno.com',
            phone: '(123) 456 - 7890',
         },
         footerLogo: [
            { logoHref: './index.html' },
            { logoSrc: './img/home/logo.svg' },
            { logoText: 'It is a long established fact that a reader will be distracted lookings.' },
            [
               {
                  footerSocialsSrc: './img/home/twitter.svg',
                  footerSocialsAlt: 'Twitter Icon',
               },
               {
                  footerSocialsSrc: './img/home/linkedin.svg',
                  footerSocialsAlt: 'Linked In Icon',
               },
            ],
         ],

         // navData: [
         //    { navHref: './index.html', navValue: 'Home' },
         //    { navHref: './project.html', navValue: 'Project' },
         //    { navHref: './blog.html', navValue: 'Blog' },
         // ],
         projFaceTab: [
            { title: 'Our Project' },
            [
               { name: 'Home', href: './index.html' },
               { name: 'Project', href: './project.html' },
            ],
         ],
         impCards
      };
   },
   methods: {
   },
}
</script>

<style lang="scss">
@import "@/assets/scss/variables";
@import "@/assets/scss/extends";

*,
*::after,
*::before {
   // box-sizing: border-box;
   padding: 0;
   margin: 0;
}

html {
   font-size: calc(100% / 16 * 10);
}

#app {
   a {
      text-decoration: none;
   }

   h1 {
      margin: 0;
   }

   font-family: 'Jost',
   sans-serif;
   font-style: normal;
   font-weight: 400;
   line-height: 1.25;
   background-color: #F4F0EC;
}
</style>
