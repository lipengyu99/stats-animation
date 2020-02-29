<template>
    <canvas class="feed-magic"></canvas>
</template>

<script>
export default {
props:{
    url:{
        type:String,
        required:true
    },
    play:{
        type:Boolean
    }
},
watch: {
    play(val){
        if(val){
            this.$render && this.$render(true)
        }
    }
},
async mounted() {
   // this.$render = await createRenderer(this.$el, this.url)
    this.$render()
    this.$emit('ready')
},
}
</script>

<style>

</style>
