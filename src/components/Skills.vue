<template>
   <section id="skills">
      <AnimateOnVisible name="fadeDown" :duration="1">
         <Title :title="content.metadata.title" :description="content.metadata.description" />
      </AnimateOnVisible>

      <div class="section-content">
         <div class="container-fluid">
            <div class="row d-flex flex-wrap align-items-center">
               <div class="col-md-2 m-auto pb-4" v-for="(post, index) in skills" :key="index">
                  <AnimateOnVisible name="bounce">
                     <img id="imgLogo" class="img-responsive mx-auto d-block" :src="getImgUrl(post.img)" :alt="post.title"/>
                     <div id="divAlt" class="altCaption text-center">{{post.title}}</div>
                  </AnimateOnVisible>
               </div>
            </div>
         </div>
      </div>
   </section>
</template>

<script>
   import Title from './Title.vue'

   export default {
      name: 'Skills',
      data () {
         return {
            skills: [
            {
               "title": "HTML",
               "img": "html.png"
            },
            {
               "title": "CSS",
               "img": "css.png"
            },
            {
               "title": "Bootstrap",
               "img": "bootstrap.png"
            },
            {
               "title": "Tailwind CSS",
               "img": "tailwind.png"
            },
            {
               "title": "Git/Github",
               "img": "Octocat.png"
            },
            {
               "title": "JavaScript",
               "img": "js.png"
            },
            {
               "title": "jQuery",
               "img": "jquery.png"
            },
            {
               "title": "Vue JS",
               "img": "vuejs.png"
            },
            {
               "title": "Vuetify",
               "img": "vuetify.png"
            },
            {
               "title": "Bootstrap Vue",
               "img": "bootstrapvue.png"
            },
            {
               "title": "Element UI",
               "img": "element-ui.png"
            },
            {
               "title": "Quasar",
               "img": "quasar.png"
            },
            {
               "title": "Nuxt JS",
               "img": "nuxt-js.png"
            },
            {
               "title": "Alpine JS",
               "img": "alpine-js.png"
            },
            {
               "title": "PHP",
               "img": "php.png"
            },
            {
               "title": "Codeigniter",
               "img": "codeigniter.png"
            },
            {
               "title": "Laravel",
               "img": "laravel.png"
            },
            {
               "title": "MySQL",
               "img": "mysql.png"
            },
            {
               "title": "PostgreSQL",
               "img": "postgresql.png"
            },
             {
               "title": "SQLite",
               "img": "sqlite.png"
            },
            {
               "title": "MongoDB",
               "img": "mongodb.png"
            },
            {
               "title": "Rest API",
               "img": "restapi.png"
            },
            {
               "title": "Firebase",
               "img": "firebase.png"
            },
            {
               "title": "Linux",
               "img": "linux.png"
            },
            ]
         }
      },
      components: {
         Title,
      },
      props: ['content'],
      methods: {
         getImgUrl(img) {
            return require('../assets/img/logo/'+img);
         },
      },
   }
</script>

<style scoped lang="scss">
   @import '@/styles/constants.scss';

   #skills {
      background-color: lighten(map-get($colors, dark), 100%);
   }

   @media(min-width: #{map-get($breakpoints, medium)}) {
      .section-content {
         width: 80%;
         margin: 0 auto;
      }
   }

   img{
      max-width: 120px;
   }

   .altCaption{
      color: map-get($colors, secondary);
      margin-top: 1rem;
   }
</style>