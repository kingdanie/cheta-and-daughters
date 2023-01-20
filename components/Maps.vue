<template>

    <div class="h-full relative">
        <div class="absolute flex justify-between w-full">
            <button class="px-3 py-2.5 bg-gray-900 hover:bg-opacity-75 flex justify-center items-center">
                <ChevronLeftIcon class="h-5 w-5 text-white" />
            </button>
            <button class="px-3 py-2.5 bg-gray-900 hover:bg-opacity-75 flex justify-center items-center">
                <ChevronRightIcon class="h-5 w-5 text-white" />
            </button>
        </div>
        <div style="width: 100%; min-height: 400px; height: 100%;">
            <iframe
                src="https://www.google.com/maps/embed?pb=!1m16!1m12!1m3!1d2965.0824050173574!2d-93.63905729999999!3d41.998507000000004!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!2m1!1sWebFilings%2C+University+Boulevard%2C+Ames%2C+IA!5e0!3m2!1sen!2sus!4v1390839289319"
                width="100%" height="100%" frameborder="0" style="border:0"></iframe>
        </div>
    </div>
</template>

<script>
import { ChevronLeftIcon, ChevronRightIcon } from '@heroicons/vue/24/solid';

export default {
    name: "Maps",
    components: { ChevronLeftIcon, ChevronRightIcon }
}
</script>

<style>
.maps {
    min-height: 400px;
    width: 100%;
    background-image: url('/img/guyana.png')
}
</style>
