<template>
    <div class="flex justify-center items-center">
        <div @click="count--" class="px-4">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                <path
                    fill="#a3a3a3"
                    d="M9.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l192 192c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L77.3 256 246.6 86.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-192 192z"
                />
            </svg>
        </div>
        <Transition>
            <div>
                <img
                    v-if="count == 1"
                    src="../../public/carousel/carousel_1.jpg"
                    class="animate-fade"
                />
                <img
                    v-if="count == 2"
                    src="../../public/carousel/carousel_2.jpg"
                    class="animate-fade"
                />
                <img
                    v-if="count == 3"
                    src="../../public/carousel/carousel_3.jpg"
                    class="animate-fade"
                />
                <img
                    v-if="count == 4"
                    src="../../public/carousel/carousel_4.jpg"
                    class="animate-fade"
                />
                <img
                    v-if="count == 5"
                    src="../../public/carousel/carousel_5.jpg"
                    class="animate-fade"
                />
            </div>
        </Transition>
        <div @click="count++" class="px-4">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512">
                <path
                    fill="#a3a3a3"
                    d="M310.6 233.4c12.5 12.5 12.5 32.8 0 45.3l-192 192c-12.5 12.5-32.8 12.5-45.3 0s-12.5-32.8 0-45.3L242.7 256 73.4 86.6c-12.5-12.5-12.5-32.8 0-45.3s32.8-12.5 45.3 0l192 192z"
                />
            </svg>
        </div>
    </div>
</template>

<script>
import { TransitionBeforePreparationEvent } from "astro/virtual-modules/transitions-events.js";
import { ref } from "vue";

export default {
    components: { TransitionBeforePreparationEvent },
    setup() {
        let count = ref(1);
        return {
            count,
        };
    },
};
</script>

<style>
svg {
    width: 25px;
    height: 25px;
}
.v-move,
.v-enter-active,
.v-leave-active {
    transition: 0.3s ease;
}

.v-enter-from,
.v-leave-to {
    opacity: 0;
    transform: translateY(10px);
}
</style>