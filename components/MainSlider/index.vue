<template>
    <div
        v-if="items && items.length"
        class="carousel-wrapper main-slider"
    >
        <div v-swiper:mySwiper="options">
            <div class="swiper-wrapper">
                <div 
                    v-for="(item,index) in items" 
                    :key="index" 
                    class="main-slider__slide img-warpper swiper-slide"
                >
                    <img 
                      :src="require(`~/assets/images/${item.img}`)" 
                      :alt="item.title" 
                    />

                    <div class="main-slider__info flex justify-start align-center absolute bottom-0 right-0 h-full w-full">
                        <div
                            v-if="item.info" 
                            class="main-slider__items flex flex-col justify-center p-2 md:p-10"
                        >
                            <div class="main-slider__item">
                                <span class="title inline-block py-1 px-5 mr-2 mb-2 ml-4 font-medium text-white rounded-lg border border-white">
                                    {{ 'ژانر' }}
                                </span>
                            
                                <span class="desc text-white">
                                    {{ item.info.tags }}
                                </span>
                            </div>

                            <div class="main-slider__item">
                                <span class="title inline-block py-1 px-5 mr-2 mb-2  ml-4 font-medium text-white rounded-lg border border-white">
                                {{ 'مدت زمان' }}
                                </span>
                            
                                <span class="desc text-white">
                                    {{ item.info.duration }}
                                </span>
                            </div>

                            <div class="main-slider__item rank">
                                <span class="title inline-block py-1 px-5 mr-2 mb-2  ml-4 font-medium text-white rounded-lg border border-white">
                                    {{ 'IMDb' }}
                                </span>
                                
                                <span class="desc font-medium text-[#FF4E7B] font-bold">
                                    {{ item.info.rate }}
                                </span>
                            </div>

                            <div class="main-slider__item">
                                <span class="title inline-block py-1 px-5 mr-2 mb-2  ml-4 font-medium text-white rounded-lg border border-white">
                                    {{ 'محصول' }}
                                </span>
                                
                                <span class="desc text-white">
                                    {{ item.info.country}}
                                </span>
                            </div>

                            <p class="main-slider__synapsis w-[280px] md:w-[350px]">
                                {{ item.description }}
                            </p>
                            
                            <div class="main-slider__button">
                                <button 
                                    type="button" 
                                    class="flex justify-center items-center font-bold text-gray-900 bg-white border border-gray-300 focus:outline-none hover:bg-gray-100 focus:ring-4 focus:ring-gray-200 font-medium rounded-lg text-sm px-10 py-2.5 mr-2 mb-2 inline-block"
                                >
                                    <svg class="ml-2 w-4 h-4 text-gray-800 dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 10 16">
                                        <path d="M3.414 1A2 2 0 0 0 0 2.414v11.172A2 2 0 0 0 3.414 15L9 9.414a2 2 0 0 0 0-2.828L3.414 1Z"/>
                                    </svg>
                                    {{ 'ورود و تماشا' }}
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
          <!-- <div class="swiper-pagination swiper-pagination-bullets"></div> -->
        </div>
    </div>
</template>

<script>
export default {
    name:'mainSlider',

    /**
     * @inheritdoc
     */
    data() {
      return {
          options: {
              slidesPerView: 1,
              loop: true,
          }
      }
    },

    props:{
        /**
         * list of items
        */
       items:Array,
    }
}
</script>

<style lang="scss" src="./index.scss" />
