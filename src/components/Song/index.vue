<template>
    <div>
      <div class="songlist" v-for="(item,index) in data.alllist" :key="index" @click="detail">
            <b style="display:block;margin-bottom:20px">{{item.name}}</b>
            <span style="margin-right:20px">{{item.artist}}</span><span>播放:{{item.playcnt}}</span>
            <i class="iconfont icon-jiantou iconsong"></i>
        </div>
    </div>
</template>
<script>
export default {
    name:"song",
    data(){
        return {
            alllist:[]
        }
    },
    props:{
        data:Object,
    },
    created() {
        // console.log(this.data)
    },
       methods: {
       detail(){
           if(this.data.type==="儿歌"){
           this.$router.push("/detail")
           }else{
               return
           }
       }
   },
}
</script>