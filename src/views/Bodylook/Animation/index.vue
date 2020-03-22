<template>
    <div>
        <div class="animatelist" v-for="(item,index) in animatedata" :key="index">
            <div class="imgs">
                <img :src="item.pic" alt="">
                <span class="nice">{{item.score}}分</span>
            </div>
            <b>{{item.name}}</b>
            <p>共{{item.method}}集</p>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return {
            animatedata:[]
        }
    },
    created() {
        this.$http.getanimate({
            type:"getlistv2",act:"home",pagesize:30,pid:26
        }).then(res=>{
            const {list,nav}=res.data
            this.animatedata=list.splice(1)
            // console.log(res.data)
        })
    },
}
</script>