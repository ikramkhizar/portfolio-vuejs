<template>
   <header class="header parallax">
      <div class="name">
         <div class="wrapper-name">
            <AnimateOnVisible name="fadeDown" ::duration="1">
               <h1>Ikram Khizer</h1>
            </AnimateOnVisible>
            <hr />
            <AnimateOnVisible name="fadeUp" ::duration="1">
               <p>Full Stack Developer</p>
            </AnimateOnVisible>
            <AnimateOnVisible name="fadeUp" ::duration="1">
               <div class="hire-btn">
                  <a href="https://www.upwork.com/freelancers/~0117cbe54d6283a4a0" class="btn btn-outline-secondary px-5 py-3 text-white"
                     target="_blank">HIRE ME</a>
               </div>
            </AnimateOnVisible>
         </div>
      </div>
   </header>
</template>

<script>
   export default {
      name: "LandingPage",
   };
</script>

<style scoped lang="scss">
   @import "@/styles/constants.scss";

   .header {
      padding: 20px;
      background-color: map-get($colors, dark);
   }

   .parallax {
      background-image: url("../assets/img/bg.jpg");
      background-attachment: fixed;
      background-position: center;
      background-repeat: no-repeat;
      background-size: cover;
      height: 100%;
   }

   .hire-btn {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 15px;

      .btn {
         border-radius: 15px;
         font-size: 1em;
      }
   }

   .name {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 100%;
      margin: 0 auto;
      z-index: 400;

      .wrapper-name {
         width: 250px;
      }

      h1 {
         font-size: 2.3rem;
         padding: 2px 10px;
         text-align: center;
         text-transform: uppercase;
         color: whitesmoke;
      }

      p {
         font-size: 1.5rem;
         text-align: center;
         margin: 5px auto;
         color: whitesmoke;
      }

      hr {
         border: 1px solid whitesmoke;
      }
   }

   @media (min-width: #{map-get($breakpoints, small)}) {
      .name {
         .wrapper-name {
            width: 55%;
         }
         h1 {
            font-size: 2.8rem;
            padding: 4% 8%;
         }
         p {
            font-size: 2rem;
         }
      }
   }
   @media (min-width: #{map-get($breakpoints, medium)}) {
      .name {
         .wrapper-name {
            width: 450px;
         }
         h1 {
            font-size: 4rem;
            padding: 4% 10%;
         }
         p {
            font-size: 2.5rem;
         }
      }
   }
   @media only screen and (max-device-width: 1024px) {
      .parallax {
         background-attachment: scroll;
      }
   }
</style>