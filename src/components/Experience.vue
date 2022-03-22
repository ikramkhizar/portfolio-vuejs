<template>
   <section id="experience">
      <AnimateOnVisible name="fadeDown" :duration="1">
         <Title class="title" title="Client Feedback" description="What my clients say about me and my work" />
      </AnimateOnVisible>

      <AnimateOnVisible name="fadeUp" :duration="1">
         <div class="container-fluid text-white">
            <div class="row text-center">
               <ExperienceColumn :reviews="leftReviews" class="col-12 col-md left" />
               <ExperienceColumn :reviews="rightReviews" class="col-12 col-md right" />
            </div>
         </div>
      </AnimateOnVisible>
   </section>
</template>

<script>
   export default {
      name: "Experience",
      props: ["content"],
      components: {
         Title: () => import('./Title'),
         ExperienceColumn: () => import('./ExperienceColumn'),
      },
      data: () => ({
         leftReviews: [
            {
               id: 1,
               title: 'Tony Alexander',
               description: `"It was a great experience working with him because is very efficient with coding and delivered great quality! I would strongly recommend Ikram and would look forward to any future works I may have with him."`
            },
            {
               id: 2,
               title: 'Taras Hill',
               description: `"He is a great guy, helpful, communicative, understanding, and skillful. If you are hesitating then take my word for it:  You won't regret working with him!"`
            },
            {
               id: 3,
               title: 'Gary Kevin',
               description: `"Ikram did a great job coding laravel as a part of our team. I can surely recommend him!"`
            },
         ],
        rightReviews: [
            {
               id: 4,
               title: 'Steven Hardy',
               description: `"Ikram was amazing. He got the tasks completed effectively and efficiently. He suggested tasks that I forgot about It was great working with Ikram, I will definitely hire in the future!"`
            },
            {
               id: 5,
               title: 'Luciano Niro',
               description: `"Ikram is totally awesome. Works very hard and gets the tasks complete first time. Really enjoy working with him."`
            },
            {
               id: 6,
               title: 'Basit Channa',
               description: `"Ikram is a talented developer with good communication."`
            },
         ],
      }),
   };
</script>

<style scoped lang="scss">
   @import "@/styles/constants.scss";

   $linear: map-get($colors, dark);

   #experience {
      background-color: lighten(map-get($colors, primary), 5%);
   }

   .title {
      color: map-get($colors, light) !important;
   }

   .row {
      padding-top: 20px;
      text-align: center;
   }

   @media (min-width: #{map-get($breakpoints, small)}) {
      .left {
         border-right: 2px solid $linear;
      }
   }

   @media (max-width: #{map-get($breakpoints, small)}) {
      .right {
         margin-top: 25px;
      }
      .left:before {
         content : "";
         position: absolute;
         left    : 20%;
         bottom  : 0;
         height  : 2px;
         width   : 60%;  /* or 100px */
         border-bottom:2px solid $linear;
      }
   }

   /deep/ .text-wrapper {
      &:after {
         border-bottom: 1px solid map-get($colors, dark) !important;
      }
   }
</style>
