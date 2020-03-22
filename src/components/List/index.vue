<template>
    <div>

              <div class="listnav" v-for="(item,index) in alldata" :key="index">


                 <div class="imgs">
                     <img :src="item.pic">
                 </div>
                 <div class="titleRight">
                     <b style="display:block;margin-bottom:20px">{{item.name}}</b>
                    <span style="margin-right:20px">{{item.artist}}</span><span>播放:{{item.playcnt}}</span>
                    <i class="iconfont icon-Shapecopy icon"></i>
                 </div>
                 
                 </div>
      
        
    </div>
</template>
<script>
export default {
    name:"list",
    data(){
        return {
            aldata:[]

        }
    },
    props:{
        alldata:Array
    },
    // watch: {
    //     alldata:{
    //     handler(newName, oldName) {
    //         this.aldata=newName
    //      console.log(newName);
    //     },
    //     deep:true
    //     }
    // },
   created() {
       console.log(this.aldata)
   },

}
</script>