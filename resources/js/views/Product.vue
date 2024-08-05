<template>
    <div class="container">
        <div class="product">
            <div class="product__images">
                <Carousel></Carousel>
            </div>
            <div class="product__details">
                <p class="product__subtitle">Sneaker company</p>
                <h1 class="product__title">Fall Limited Edition Sneakers</h1>
                <p class="product__description">These low-profile sneakers are your perfect casual wear companion.
                    Featuring a durable rubber outer sole, they'll withstand everything the weather can offer.</p>
                <div class="product__price-details">
                    <p class="product__price">$125.00 <span class="product__discount">50%</span> </p>
                    <p class="product__original_price">$250.00</p>
                </div>
                <div class="product__quantity-details">
                    <div class="product__quantity">
                        <button class="product__quantity-minus" @click="decrease()">
                            <img src="/images/icon-minus.svg" alt="minus-button">
                        </button>

                        <input class="product__quantity-input" type="number" min="0" v-model="quantity">

                        <button class="product__quantity-plus" @click="increase()">
                            <img src="/images/icon-plus.svg" alt="plus-button">
                        </button>
                    </div>
                    <Button>
                        <template #submitBtn>
                            Add to cart
                        </template>
                        <template #icon>
                            <svg width="22" height="20" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M20.925 3.641H3.863L3.61.816A.896.896 0 0 0 2.717 0H.897a.896.896 0 1 0 0 1.792h1l1.031 11.483c.073.828.52 1.726 1.291 2.336C2.83 17.385 4.099 20 6.359 20c1.875 0 3.197-1.87 2.554-3.642h4.905c-.642 1.77.677 3.642 2.555 3.642a2.72 2.72 0 0 0 2.717-2.717 2.72 2.72 0 0 0-2.717-2.717H6.365c-.681 0-1.274-.41-1.53-1.009l14.321-.842a.896.896 0 0 0 .817-.677l1.821-7.283a.897.897 0 0 0-.87-1.114ZM6.358 18.208a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm10.015 0a.926.926 0 0 1 0-1.85.926.926 0 0 1 0 1.85Zm2.021-7.243-13.8.81-.57-6.341h15.753l-1.383 5.53Z"
                                    fill="currentColor" fill-rule="nonzero" />
                            </svg>
                        </template>
                    </Button>
                </div>
            </div>

        </div>

    </div>

</template>

<script>
import Carousel from "../../components/carousel.vue"
import Button from "../../components/button.vue"


export default {
    data() {
        return {
            quantity: 0
        }
    },

    components: {
        Carousel,
        Button
    },

    methods: {
        increase() {
            this.quantity++
        },
        decrease() {
            if (this.quantity > 0) {
                this.quantity--
            }
        },

    }

}
</script>
