<template>
    <section 
        v-if="items && items.length"
        class="categories mt-5 mb-5 flex justify-between flex-wrap"
    >
        <div  
            v-for="(item,index) in items"
            :key="index"
            class="categories__item flex justify-center items-end mb-3 md:m-0"
        >
            <img 
                :src="require(`~/assets/images/${item.img}`)" 
                :alt="item.title" 
            />
        </div>
    </section>
</template>

<script>
export default {
    name:'Categories',

    props:{
        /**
         * list of items
         */
        items:Array,
    }
}
</script>
