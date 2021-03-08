<template>
    <div id="app">
        <router-view/>
        <FooterGuide v-show="$route.meta.showFooter"/>
    </div>
</template>

<script>
import {mapActions} from 'vuex'
import FooterGuide from './components/FooterGuide/FooterGuide.vue'

export default {

    mounted(){
        this.getAddress()//第二种方法任选一种
        this.getUserInfo()
        //this.$store.dispatch('getAddress')
    },
    methods:{
        ...mapActions(['getAddress','getUserInfo'])
    },
    components:{
        FooterGuide
    }

}
</script>

<style lang="stylus" ref="stylesheet/stylus">
    .app
        width 100%
        height 100%
        background #f5f5f5
</style>