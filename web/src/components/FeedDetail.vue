<template>
<transition name="show" @enter="handleEnter" @after-enter="handleAfterEnter">
     <div class="feed-detail" v-if="selected"
     :class="{'feed_detail__stat':isShowStat}" >
    <feed-magic
        v-if="isShowMagic"
        :url="selected.feed.coverUrl"
        :play="isShowStat"
        @ready="handleReady"
      />
    </div>
</transition>
   
</template>

<script>
import { mapState } from "vuex";
import FeedMagic from './FeedMagic.vue'
export default {
    components:{
        "feed-magic":FeedMagic,
    },
    data() {
        return {
            isShowMagic:false,
            isShowStat:false,
            isMagicReady:false
        }
    },
    computed: {
        ...mapState(['selected'])
    },
    methods: {
        handleEnter(){
            const top = this.selected.rect.top-141+53
            const feed = this.$refs.feed

            feed.$el.style.transform = `translate3d(0,${top}px,0)`
            setTimeout(() => {
                feed.$el.style.transform = ''
            }, 0);
        },
       handleAfterEnter () {
            setTimeout(() => {
        this.isShowMagic = true
      }, 600)
    },

    },
}
</script>

<style>

</style>
