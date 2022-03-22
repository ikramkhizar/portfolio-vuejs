<template>
    <section id="about">
        <AnimateOnVisible name="fadeDown" :duration="1">
            <Title title="ABOUT ME" description="HOPE TO KNOW YOU AFTER" />
        </AnimateOnVisible>

        <AnimateOnVisible name="fadeRight" :duration="1">
            <div class="section-content">
                <div class="container-fluid">
                    <div class="row justify-content-center">
                        <Photo />
                    </div>
                    <div class="row">
                        <div class="col-md-7 mr-auto card-mobile">
                            <Presentation />
                        </div>
                        <div class="col-md-4 card-mobile">
                            <PersonnalCard />
                        </div>
                    </div>
                </div>
            </div>
        </AnimateOnVisible>
    </section>
</template>

<script>
    export default {
        name: 'AboutMe',
        components: {
            Title: () => import('./Title'),
            PersonnalCard: () => import('./PersonnalCard'),
            Presentation: () => import('./Presentation'),
            Photo: () => import('./Photo')
        },
    }
</script>

<style scoped lang="scss">
    @import '@/styles/constants.scss';

    #about {
        background-color: lighten(map-get($colors, dark), 100%);
    }

    @media(min-width: #{map-get($breakpoints, medium)}) {
        .section-content {
            width: 80%;
            margin: 0 auto;
        }
    }

    @media(max-width: #{map-get($breakpoints, medium)}) {
        .card-mobile {
            text-align: center !important;
            margin-top: 20px;
        }
    }
</style>