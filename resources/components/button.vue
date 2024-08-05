<template>
    <div>
        <button type="submit" class="product__submitBtn">
            <div v-if="$slots.icon" class="mr-20">
                <slot name="icon"></slot>
            </div>
            <slot name="submitBtn"></slot>
        </button>

    </div>

</template>

<script>
export default {
    data() {
        return {

        }
    },

}
</script>

<style lang="scss">
@import 'resources/css/app.scss';


.product__submitBtn {
    width: 100%;
    padding: 20px 40px;
    @include dflex(center, center);
    border-radius: 10px;
    @include border-outline-none;
    background-color: $Orange;
    color: $White;
    cursor: pointer;
    font-size: large;
    font-weight: 600;
    box-shadow: 0px 10px 20px 20px $Pale-orange;
}

@media screen and (min-width: 1025px) {

    .product__submitBtn {
        @include dflex(space-between, center);
        padding: 15px 70px;
        font-size: medium;
    }

}
</style>
