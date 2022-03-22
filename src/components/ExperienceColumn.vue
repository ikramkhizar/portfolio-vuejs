<template>
   <div>
      <div class="resume-item pb-3 border-bottom" v-for="(review, index) in reviews" :key="index">
         <div class="resume-description pb-2">
            <strong class="color-light" v-html="review.title"></strong>
         </div>
         <div class="color-darker" v-html="review.description"></div>
      </div>
   </div>
</template>

<script>
   export default {
      name: "ExperienceColumn",
      props: ["reviews"],
   };
</script>

<style scoped lang="scss">
   @import "@/styles/constants.scss";

   $linear: map-get($colors, light);
   .resume-item {
      margin-bottom: 20px;
      p {
         font-size: 1.5rem;
         margin-top: 0;
      }
      .resume-description {
         font-size: 1.7rem;
      }
      .year {
         font-weight: 600;
         margin-bottom: 5px;
      }
   }
   .color-light {
      color: map-get($colors, light);
   }
   .color-darker {
      color: map-get($colors, dark);
   }
</style>
