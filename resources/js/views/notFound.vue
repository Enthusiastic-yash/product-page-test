<template>
    <div>
        <div class=" not-found-wrapper">
            <img src="/images/404.png" alt="404-page-not-found">
            <Button @click="$router.push('/')">
                <template #submitBtn>
                    continue shoping
                </template>

            </Button>
        </div>
    </div>
</template>

<script>
import Button from "../../components/button.vue"
export default {
    data() {
        return {

        }
    },

    components: {
        Button,
    },
}

</script>
<style lang="scss">
@import 'resources/css/app.scss';

.not-found-wrapper {
    width: 100%;
    min-height: 100vh;
    flex-direction: column;
    overflow: hidden;
    @include dflex(center, center);

    img {
        width: 400px;
        height: auto;
    }

}
</style>