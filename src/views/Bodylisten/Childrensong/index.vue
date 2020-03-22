<template>
    <div>
        <song :data="{alllist,type}"/>
    </div>
</template>
<script>
export default {
    data(){
        return {
            alllist:[],
            type:"儿歌"
        }
    },
    created() {
        this.$http.getsong({
            type:"getlist",pagesize:30,listid:5
        }).then(res=>{
            const {list}=res.data
            this.alllist=list.splice(1)
        })
    },
}
</script>