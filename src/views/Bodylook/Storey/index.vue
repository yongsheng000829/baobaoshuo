<template>
    <div>
           <list :alldata="listdata"/>
    </div>
</template>
<script>
export default {
    data(){
        return {
            listdata:[]

        }
    },
    created() {
        this.$http.getstory({
            type:"getvideos",pagesize:30,collectid:27
        }).then(res=>{
            const {list,nav}=res.data
            this.listdata=list.splice(1)
        })
    },
}
</script>