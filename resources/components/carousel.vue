<template>
    <div>
        <Carousel id="gallery" :items-to-show="1" :wrap-around="false" v-model="currentSlide">
            <Slide v-for="slide in images" :key="slide">
                <div class="carousel__item">
                    <img :src="`/images/image-product-${slide}.jpg`" alt="product-image">
                </div>
            </Slide>

            <template #addons>
                <Navigation />
            </template>
        </Carousel>
        <div class="gallery__thumbnails">
            <Carousel id="thumbnails" :items-to-show="4" :wrap-around="false" v-model="currentSlide" ref="carousel">
                <Slide v-for="(slide, index) in images" :key="index">
                    <div class="carousel__item " @click="slideTo(slide - 1)">
                        <div class="child-thumbnails" :class="{ 'active-thumbnail': currentSlide === index }">
                            <div class="img-wrapper">
                                <img :src="`/images/image-product-${slide}.jpg`" alt="product-images">
                            </div>
                        </div>
                    </div>

                </Slide>
            </Carousel>

        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue'
import { Carousel, Slide, Navigation, Pagination } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
    name: 'Gallery',
    components: {
        Carousel,
        Slide,
        Navigation,
        Pagination

    },
    data: () => ({
        currentSlide: 0,
        images: ['1', '2', '3', '4']
    }),
    methods: {
        slideTo(val) {
            this.currentSlide = val
        },
    },
})
</script>
<style lang="scss">
@import 'resources/css/app.scss';

.carousel__prev,
.carousel__next {
    background-color: $White;
    border-radius: 50%;
    color: $Black;
    padding: 10px;
    margin: 0 15px;
}

#thumbnails {
    display: none;
}

@media screen and (min-width: 1025px) {

    .carousel__prev,
    .carousel__next {
        display: none;
    }

    .carousel__item {
        @include dflex(center, null);
    }

    .carousel__item img {
        border-radius: 10px;
    }

    #thumbnails {
        display: block;
    }

    .gallery__thumbnails {
        position: absolute;
        bottom: -110px;
    }

    .child-thumbnails {
        width: 80%;
    }

    .active-thumbnail {
        position: relative;

        .img-wrapper {
            position: relative;

            &::before {
                content: "";
                position: absolute;
                left: 0;
                width: 100%;
                height: 95%;
                background-color: $Light-grayish-blue;
                border: 3px solid $Orange;
                border-radius: 7px 10px 10px 9px;
                opacity: 0.7;
            }
        }
    }



}
</style>
