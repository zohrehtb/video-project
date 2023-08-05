<template>
    <section
        v-if="items && items.length"
        class="carousel-wrapper movie-slider mb-10 relative"
    >
        <header class="font-bold border-t border-[#6750A4] border-solid leading-[30px] py-3">
            {{ title }}
        </header>
         <div v-swiper:mySwiper="options">
            <div class="swiper-wrapper">
                <div 
                    v-for="(item, index) in items"
                    :key="index" 
                    class="movie-slider__item img-warpper swiper-slide"
                >
                    <div 
                        class="movie-slider__image mb-4"
                        :style="{height:height}"
                    >
                        <img 
                        :src="require(`~/assets/images/${item.img}`)" 
                        :alt="item.title" 
                    />
                    </div>

                    <div 
                        class="movie-slider__info"
                        :class="multimedia ? ' absolute bottom-0 right-0 w-full' : ''"
                    >
                        <h3 
                            class="font-bold mb-3" 
                            :class="multimedia ? 'text-white text-[20px] ' : 'text-black text-[16px]'"
                        >
                            {{ item.title }}
                        </h3>
                        <p 
                            v-if="description" 
                            :class="multimedia ? 'hidden' : 'text-[#625B71] text-[15px] leading-[30px]'"
                        >
                            {{ item.description }}
                        </p>   
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name:'movieSlider',

    props:{
        /**
         * list of items
         */
        items:Array,

        /**
         * Active description
         */
        description:Boolean,

        /**
         * Active Multimedia
         */
        multimedia:Boolean,

        /**
         * Active Cols
         */
        cols:{
            type: String,
            default: '5',
        },

        /**
         * image height
         */
        height:String,

         /**
         * title
         */
        title:String,
    },

    data() {
      return {
          options: {
                slidesPerView: this.cols,
                loop: true,
                autoplay:true,
                hasNavigation:true,
                slideToClickedSlide: true,
                navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev'
                    },
                breakpoints: {
                    1200: {
                        slidesPerView: 4,
                    },
                    992: {
                        slidesPerView: 2.2,
                    },
                    448: {
                        slidesPerView: 1.2,
                    },
                },
          }
      }
    }

}
</script>

<style lang="scss" src="./index.scss" />
