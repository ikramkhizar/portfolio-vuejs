<template>
   <section id="projects">
      <AnimateOnVisible name="fadeDown" :duration="1">
         <Title class="title" title="My Projects" description="This is my story"/>
      </AnimateOnVisible>

      <div class="container-fluid center-block">
         <article class="content text-center">
            <AnimateOnVisible class="timeline mx-auto" v-for="(post, index) in projects" :key="index" name="fadeLeft" :duration="0.5">
               <vue-timeline-update :date="new Date(post.date)" :title="post.title" :description="post.content" :thumbnail="getImgUrl(post.image)"
                  :color="post.color" :category="post.tag" icon="code"/>
            </AnimateOnVisible>
         </article>
      </div>
   </section>
</template>

<script>
   export default {
      name: "Projects",
      data () {
         return {
            projects: [
            {
               "title": "Telemart",
               "content": "Telemart, is a known name in the e-commerce sphere of Pakistan, owned by Tradelink enterprise. The parent company, Tradelink, has been dealing in electronics and selling mobile phones in Pakistan since 1991.<br><br>Link : <a href='https://www.telemart.pk/'>https://www.telemart.pk/</a>",
               "link": "https://www.telemart.pk/",
               "image": "telemart.png",
               "tag": "Ecommerce",
               "color": "blue",
               "date": "2022-03-22"
            },
            {
               "title": "Complaint Registration Portal Pakistan",
               "content": "Web Based Portal for customers and officials to file, track and manage consumer service complaints.!<br><br>Link : <a href='https://consumerservice.punjab.gov.pk/'>https://consumerservice.punjab.gov.pk/</a>",
               "link": "https://consumerservice.punjab.gov.pk/",
               "image": "consumerservice.png",
               "tag": "Software",
               "color": "red",
               "date": "2020-05-02"
            },
            {
               "title": "Kabayan Remit",
               "content": "Kabayan Remit provides a fast, affordable, and convenient way of sending money to the Philippines.<br><br>Link : <a href='https://kabayanremit.com/'>https://kabayanremit.com/</a>",
               "link": "https://kabayanremit.com/",
               "image": "kabayanremit.png",
               "tag": "Software",
               "color": "red",
               "date": "2021-04-12"
            },
            {
               "title": "Venderei",
               "content": "Venderei is a humanized platform, focused on giving you personalized support to help you create your products and sell on a high scale from the beginning!<br><br>Link : <a href='https://venderei.com/'>https://venderei.com/</a>",
               "link": "https://venderei.com/",
               "image": "venderei.png",
               "tag": "Saas",
               "color": "green",
               "date": "2020-12-08"
            },
            {
               "title": "Spooray",
               "content": "Spooray – The Party App That Sprays Cash Virtually.<br><br>Link : <a href='https://spooray.com/'>https://spooray.com/</a>",
               "link": "https://spooray.com/",
               "image": "spooray.png",
               "tag": "Software",
               "color": "red",
               "date": "2021-12-28"
            },
            {
               "title": "Photograpshs by Steven",
               "content": "Bringing his photography to life.<br><br>Link : <a href='https://photographsbysteven.shop/'>https://photographsbysteven.shop/</a>",
               "link": "https://photographsbysteven.shop/",
               "image": "photographsbysteven.png",
               "tag": "Ecommerce",
               "color": "blue",
               "date": "2022-03-11"
            },
            ]
         }
      },
      components: {
         Title: () => import('./Title'),
      },
      methods: {
         getImgUrl(img) {
            if(img == undefined || img == "") return ""
            return require('../assets/img/projects/'+img)
         },
      },
   };
</script>

<style scoped lang="scss">
   @import "@/styles/constants.scss";

   $linear: map-get($colors, dark);

   #projects {
      background-color: lighten(map-get($colors, primary), 5%);

   }

   .title {
      color: map-get($colors, light) !important;
   }

   /deep/ .text-wrapper {
      &:after {
         border-bottom: 1px solid map-get($colors, dark) !important;
      }
   }

   article .inner {
      position: relative;
      display: inline-block;
      vertical-align: middle;
      z-index: 1;
   }

   .content {
      color: map-get($colors, light);
      margin-top: 30px;
      header {
         height: 100%;
         width: 70%;
      }
      h1{
         font-size: 3rem;
      }
   }

   .vertical-center {
      display: flex;
      align-items: center;
   }

   h1 {
      margin-top: 10px;
      margin-bottom: 20px;
   }
</style>
