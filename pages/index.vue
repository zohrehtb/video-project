<template>
    <div>
        <c-header/>
        <main>
            <c-slider :items="mainSliderItems"/>
            <div class="container mx-auto p-[15px] md:p-0">
                <c-categories :items="categoriesItems"/>

                <c-movie-slider 
                    :title="titles.sepcial" 
                    :items="filterPosts('sepcial')"
                    description
                    height="133px"
                />

                <c-movie-slider 
                    :title="titles.new" 
                    :items="filterPosts('new')"
                    height="133px"
                />

                <c-movie-slider 
                    :title="titles.next" 
                    :items="filterPosts('next')"
                    height="170px"
                    cols="4"
                />

                <c-movie-slider 
                    :title="titles.your" 
                    :items="filterPosts('your')"
                    height="133px"
                />
            </div>

            <c-pinned-post :content="pinnedItem" />

            <div class="container mx-auto p-[15px] md:p-0">

                <c-movie-slider 
                    :title="titles.updated" 
                    :items="filterPosts('updated')"
                    height="133px"
                />

                <c-movie-slider 
                    :title="titles.seen" 
                    :items="filterPosts('seen')"
                    height="133px"
                />

                <c-movie-slider 
                    :title="titles.your_favorite" 
                    :items="filterPosts('sepcial')"
                    description
                    height="133px"
                />
            </div>
        </main>
        <c-footer />
    </div>
</template>

<script>
/** Data */
import json from '../static/data';

/** Components */
import CHeader from '../components/Header'
import CFooter from '../components/Footer'
import CSlider from '../components/MainSlider'
import CCategories from '../components/Categories'
import CPinnedPost from '../components/PinnedMovie'
import CMovieSlider from '../components/MovieSlider'

export default {
  name: 'IndexPage',

  /**
   * @inheritdoc
  */
  data() {
      return {
          mainSliderItems: json.data.main_slider,
          categoriesItems: json.data.categories,
          pinnedItem: json.data.pinned_movie,
          moviesItems: json.data.movies,
          titles:{
            new: 'تازه‌ها',
            hot: 'داغ ترین',
            your: 'به تماشا ادامه دهید',
            updated: 'سریال‌های به‌روز شده',
            next: 'بزودی',
            sepcial: 'عناوین ویژه',
            seen:'دیده‌ شده‌ها',
            your_favorite:'چون این سریال‌ها را دیده‌اید'
          },
      };
  },

  components:{
      CHeader,
      CSlider,
      CFooter,
      CCategories,
      CPinnedPost,
      CMovieSlider,
  },

  methods:{
    /**
     * Filter posts by category
     *
     * @param {*} slug
     * @returns {*}
     */
    filterPosts(slug) {
        this.filteredPosts = [];
        this.moviesItems.forEach((post) => {
            if (post.category && post.category.length) {
                post.category.forEach((cat) => {
                    if (cat.name === slug) {
                        this.filteredPosts.push(post);
                    }
                });
            }
        });

        return this.filteredPosts;
    },
  }
}
</script>
