<template>
   <section id="projects">
      <AnimateOnVisible name="fadeDown" :duration="1">
         <Title
         class="title"
         :title="content.metadata.title"
         :description="content.metadata.description"
         />
      </AnimateOnVisible>

      <div class="container-fluid center-block">
         <article class="content text-center">

            <AnimateOnVisible class="timeline mx-auto" v-for="(post, index) in projects" :key="index" name="fadeLeft" :duration="0.5">
               <vue-timeline-update
               :date="new Date(post.date)"
               :title="post.title"
               :description="post.content"
               :thumbnail="getImgUrl(post.image)"
               :color="post.color"
               :category="post.tag"
               icon="code"
               />
            </AnimateOnVisible>
         </article>
      </div>
   </section>
</template>

<script>
   import Title from "./Title.vue";

   export default {
      name: "Projects",
      data () {
         return {
            projects: [
            {
               "title": "IG_Automation_Bot (Work in progress)",
               "content": "Python script for Instagram automation using Instaloader. Used for auto following and DM. Easily configurable through Yaml config files!<br><br>Link : <a href='https://github.com/hbollon/IG_Automation_Bot'>https://github.com/hbollon/IG_Automation_Bot</a>",
               "link": "https://github.com/hbollon/IG_Automation_Bot",
               "image": "ig.gif",
               "tag": "Software",
               "color": "red",
               "date": "2020-11-02"
            },
            {
               "title": "Go-edlib",
               "content": "Golang string comparison and edit distance algorithms library, featuring : Levenshtein, LCS, Hamming, Damerau levenshtein (OSA and Adjacent transpositions algorithms), Jaro-Winkler, Cosine, etc.<br><br>Link : <a href='https://github.com/hbollon/go-edlib'>https://github.com/hbollon/go-edlib</a>",
               "link": "https://github.com/hbollon/go-edlib",
               "image": "edlib.jpg",
               "tag": "Library",
               "color": "blue",
               "date": "2020-08-25"
            },
            {
               "title": "Gyro'Ball",
               "content": "3D labyrinth game project for Android using Unity. Use device gyroscope.<br><br>Link : <a href='https://play.google.com/store/apps/details?id=com.BitsPlease.GyroBall&hl=fr&fbclid=IwAR0itwUAcbpAl3TgkFGiSrQz_CHTRpWjSXTQZqNGPESikdOJWZ6DIrk5qAA'>Google Play</a>",
               "link": "https://play.google.com/store/apps/details?id=com.BitsPlease.GyroBall&hl=fr&fbclid=IwAR0itwUAcbpAl3TgkFGiSrQz_CHTRpWjSXTQZqNGPESikdOJWZ6DIrk5qAA",
               "image": "gyroball.jpg",
               "tag": "Video Game",
               "color": "purple",
               "date": "2020-07-28"
            },
            {
               "title": "GyroscopeControl",
               "content": "Unity script used for smooth and customizable object rotation with gyroscope. It include initial calibration with offset, rotation speed, smoothing parameter editable in Unity inspector and debug overlay.<br><br>Link : <a href='https://github.com/hbollon/GyroscopeControl'>https://github.com/hbollon/GyroscopeControl</a>",
               "link": "https://github.com/hbollon/GyroscopeControl",
               "image": "",
               "tag": "Script",
               "color": "green",
               "date": "2020-06-17"
            },
            {
               "title": "Urbalog",
               "content": "Android adaptation of board game using Nearby Connections API and Java for the LAET<br><br>Link : <a href='https://github.com/hbollon/Urbalog'>https://github.com/hbollon/Urbalog</a>",
               "link": "https://github.com/hbollon/Urbalog",
               "image": "urba.jpg",
               "tag": "Video Game",
               "color": "purple",
               "date": "2020-05-19"
            },
            {
               "title": "android-sqlite-toolbox",
               "content": "Android java package designed to manage any sqlite database. Includes creation of the db and interactions with it (CRUD), import and export in several file formats (easily adaptable to any other format) and synchronization in http.<br><br>Link : <a href='https://github.com/hbollon/android-sqlite-toolbox'>https://github.com/hbollon/android-sqlite-toolbox</a>",
               "link": "https://github.com/hbollon/android-sqlite-toolbox",
               "image": "",
               "tag": "Library",
               "color": "blue",
               "date": "2020-05-08"
            },
            {
               "title": "Le-Parrainage-Boursorama",
               "content": "Website built with Laravel. Used to promote and manage sponsorships for a online bank. Hosted on personnal vps.<br><br>Link : <a href='https://le-parrainage-boursorama.fr'>https://le-parrainage-boursorama.fr</a>",
               "link": "https://le-parrainage-boursorama.fr",
               "image": "boursoweb.jpg",
               "tag": "Website",
               "color": "orange",
               "date": "2019-09-15"
            }
            ]
         }
      },
      props: ['content'],
      components: {
         Title
      },
      methods: {
         getImgUrl(img) {
            if(img == undefined || img == "")
               return ""
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
      color: map-get($colors, light);
   }

   /deep/ .text-wrapper {
      &:after {
         border-bottom: 1px solid map-get($colors, dark);
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
