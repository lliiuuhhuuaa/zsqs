<template>
    <div class="body">
        <img :src="pdfPath" type="application/pdf" width="100%"/>
    </div>
</template>

<script>

    export default {
        name: 'MessageBody',
        props: {
            hideHeader: Boolean
        },
        data() {
            return {
                pdfPath:"source/zsqs1.jpeg"
            }
        },
        mounted() {
            this.Emit.$on("updateBody", this.updateBody)
        },
        methods:{
            updateBody:function (obj) {
                this.pdfPath = "source/zsqs"+obj.id+".jpeg";
            }
        }


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .body {
        width: 100%;
        height: calc(100vh - 50px);
        overflow-y: auto;
    }
</style>
