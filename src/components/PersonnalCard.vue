<template>
  <div>
    <h3>Ikram Khizer</h3>
    <div class="data"><strong>E-mail:</strong> ikramkhizer@gmail.com</div>
    <div class="data"><strong>City:</strong> Faisalabad, Pakistan</div>
    <div class="data"><strong>Languages:</strong> Urdu, English</div>
    <SocialBar :links="links"/>
  </div>
</template>

<script>
import SocialBar from './SocialBar.vue'

export default {
    name: 'PersonnalCard',
    props: ['user', 'links'],
    components: {
        SocialBar,
    }
}
</script>

<style scoped lang="scss">
    @import '@/styles/constants.scss';

    .data {
        margin-bottom: 15px;
    }
</style>