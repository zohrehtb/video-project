<template>
    <section 
        v-if="content" 
        class="pinned-movie flex items-end w-full pb-10 relative"
        :style="{ backgroundImage: `url(${require('~/assets/images/' + content.img)})` }"
    >
        <p
            v-if="content.description"
            class="text-[20px] text-white absolute w-full right-0 text-center top-[10%] md:top-[30%] md:right-[10%] md:w-[300px] md:text-right md:text-[16px]"
        >
            {{ content.description }}
        </p>

        <div class="container mx-auto p-[15px] md:p-0">
            <div class="pinned-movie__screens grid grid-cols-3 md:grid-cols-6">
                <template v-if="content.screen_shots && content.screen_shots.length">
                    <div
                        v-for="(screen, index) in content.screen_shots" 
                        :key="index" 
                    >
                        <img 
                            :src="require(`~/assets/images/${screen.link}`)" 
                            alt="movie screen shot"
                        >
                        <h6 
                            v-if="screen.title" 
                            class="text-[16px] text-white mt-2"
                        >
                            {{ screen.title }}
                        </h6>
                    </div>
                </template>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name:'pinnedMovie',

    props:{
        /**
         * Content
         */
        content:Object,
    }
}
</script>

<style lang="scss" src="./index.scss" />
