<template>
    <div>
        <song :data="{alllist}"/>
    </div>
</template>
<script>
export default {
    data(){
        return {
            alllist:[]
        }
    },
    created() {
        this.$http.getstory({
            type:"getlist",pagesize:30,listid:6
        }).then(res=>{
            const {list}=res.data
            this.alllist=list.splice(1)
        })
    },
    
}
</script>