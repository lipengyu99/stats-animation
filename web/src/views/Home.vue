<template>
  <div class="home">
    <action-button/>
    <feed-list/>
    <feed-detail/>
  </div>
</template>

<script>
import ActionButton from '../components/ActionButton.vue'
import FeedList from '../components/FeedList.vue'
import FeedDetail from '../components/FeedDetail.vue'
export default {
  components:{
    "action-button":ActionButton,
    "feed-list":FeedList,
    "feed-detail":FeedDetail
  }
}
</script>

<style>
.home{
  height: 100%;
  width: 100%;
  overflow: hidden;
  background-color: #f1f2fb;
}
.heading{
    padding: 16px 30px;
    font-size: 18px;
    font-weight: 600;
}
</style>
