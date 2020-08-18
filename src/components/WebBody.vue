<template>
    <div class="body">
        <img :src="pdfPath" type="application/pdf" width="100%" v-if="id===1"/>
        <div class="text-body">
            <div v-if="id===2">
                <img :src="srcPath[0]" width="60%"/>
                <br/>
                <br/>
                海南千盛实业有限公司成立于2020年。
                <br/>
                <br/>
                注册资金1000万元，是一家集工程<br/><br/>设计服务与咨询为一体的实业企业，主要面象全国市场。
                <br/>
                <br/>
                员工人数十人，不断提升企业的核心竞争力，
                <br/>
                <br/>
                使企业在发展中树立起良好的社会形象。凭借专业的水平和成熟的技术。
                <br/>
                <br/>
                公司将始终坚持“质量第一，信誉第一”的宗旨，以科学的管理手段，雄
                <br/>
                <br/>
                厚的技术力量，将不断深化改革，创新机制，适应市场，全面发展，欢
                <br/>
                <br/>
                迎各界朋友莅临参观<br/><br/>指导和业务洽谈。
            </div>
            <div v-if="id===31">
                <img :src="srcPath[3]" width="60%"/>
                <br/>
                <br/>
                电脑图文设计制作<br/><br/>计算机专业领域的技术服务<br/><br/>企业形象策划<br/><br/>电脑网络工程<br/><br/>
                展览展示服务<br/><br/>通讯领域的技术服务<br/><br/>市场调研<br/><br/>资料翻译服务<br/><br/>摄影服务<br/><br/>礼仪服务<br/><br/>
                公关活动策划<br/><br/>赛事活动策划<br/><br/>快递服务<br/><br/>婚庆礼仪服务<br/><br/>室内保洁服务<br/><br/>餐饮管理<br/><br/>
                市政工程配套服务<br/><br/>其他居民服务<br/><br/>物业管理<br/><br/>文化艺术交流策划服务<br/><br/>房地产开发<br/><br/>
                物流<br/><br/>船务服务货运代理等。
            </div>
            <div v-if="id===32">
                <img :src="srcPath[4]" width="60%"/>
                <br/>
                <br/>
                房产信息咨询<br/><br/>商务咨询<br/><br/>家政服务咨询<br/><br/>财务咨询<br/><br/>理财咨询<br/><br/>劳务咨询<br/><br/>投资管理咨询<br/><br/>
                投资咨询<br/><br/>医疗信息咨询<br/><br/>企业管理咨询<br/><br/>人力资源咨询<br/><br/>企业营销咨询<br/><br/>投资管理<br/><br/>
                文化艺术咨询<br/><br/>法律信息咨询等等。
            </div>
            <div v-if="id===33">
                <img :src="srcPath[5]" width="60%"/>
                <br/>
                <br/>
                建筑工程<br/><br/>绿化工程<br/><br/>市政工程<br/><br/>园林工程<br/><br/>建筑设计<br/><br/>室内装潢<br/><br/>室内设计<br/><br/>景观设计。
            </div>
            <div v-if="id===34">
                <img :src="srcPath[2]" width="60%"/>
                <br/>
                <br/>
                货物<br/><br/>药品<br/><br/>技术<br/><br/>黄金及其制品等等进出口。
            </div>
            <div v-if="id===4">
                <img :src="srcPath[1]" width="60%"/>
                <br/>
                <br/>
                联系电话：0898--3281188
                <br/><br/>
                传真：0898--3281188
                <br/><br/>
                QQ:455288977
            </div>
        </div>
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
                pdfPath:"source/zsqs1.jpeg",
                id:1,
                srcPath:[]
            }
        },
        created() {
            for(let i=1;i<=6;i++){
                this.srcPath[i-1] = "source/img"+i+".jpg";
            }

        },
        mounted() {
            this.Emit.$on("updateBody", this.updateBody)
        },
        methods:{
            updateBody:function (obj) {
                this.id = obj.id;
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
    .text-body{
        padding: 50px 20%;
    }
</style>
