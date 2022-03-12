<template>
  <div class="paragraph">
    <h3>WHO AM I ?</h3>
    <div class="begin">I am a purposeful and creative developer with a proven ability to develop projects from inception through production to final delivery. I ensure that the work is effective, appropriate, and delivered within agreed timescales.</div><br>
    <p>I love solving new business and technical challenges every other day with a wide range of technologies. I understand the business value, but always pay attention to infrastructure and code quality to develop stable and scalable solutions in the long run.</p>
  </div>
</template>

<script>
export default {
    name: 'Description',
    props: ['content']
}
</script>

<style scoped lang="scss">
    @import '@/styles/constants.scss';

    .paragraph {
        color: map-get($colors, primary);
        .begin {
            color: map-get($colors, secondary);
        }
    }
</style>