<template>
   <article id="project-face" class="project-face">
      <div class="project-face__content">
         <div class="project-face__tab">
            <h2 class="project-face__title">{{ projfacetab[0].title }}</h2>
            <p class="project-face__anchor"><a :href="projfacetab[1][0].href">{{ projfacetab[1][0].name }}</a> / <a
                  :href="projfacetab[1][1].href">{{ projfacetab[1][1].name }}</a></p>
         </div>
      </div>
   </article>
</template>

<script>
export default {
   name: 'ProjectFaceContent',
   props: {
      projfacetab: Array,
   }

}
</script>

<style lang="scss" scoped>
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
</style>