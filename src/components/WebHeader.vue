<template>
  <div class="head">
    <div class="title-item child-item" v-for="item in titles" v-bind:key="item.id" @mouseover="activeId=item.id" @mouseout="activeId=-1" @click="updateBody(item)">
      <div class="title-child" v-if="item.child" v-bind:class="{'active':item.id==activeId}">
        <div class="child-item" v-for="it in item.child" v-bind:key="it.id" @click="updateBody(item)">
          {{it.name}}
        </div>
      </div>
      {{item.name}}
    </div>
  </div>
</template>

<script>
export default {
  name: 'MessageHeader',
  data(){
    return {
      titles:[{id:1,name:"首页"},
        {id:2,name:"关于我们"},
        {id:3,name:"服务范围",child:[{id:31,name:"服务类"},{id:32,name:"咨询类"},{id:33,name:"工程设计类"},{id:34,name:"服务类"},]},
        {id:4,name:"联系我们"}],
      activeId:-1
    }
  },
  methods:{
    updateBody:function (item) {
      console.log(item)
      if(item.child){
        return;
      }
      //发送
      this.Emit.$emit("updateBody",{id:item.id});
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head{
  background: #EEEEEE;
  height: 50px;
  color: #000;
}
.head .title-item{
  width: 25%;
  float: left;
  text-align: center;
  height: 50px;
  line-height: 50px;
  cursor: pointer;
}
.head .child-item{
  border-top:1px solid #EEE;
}
.head .child-item:hover{
  background: #0099CC;
  color: #FFF;
  border-top:1px solid #FFF;
}
.title-child{
  width: 25%;
  background: #FFF;
  color: #000;
  position: absolute;
  top:50px;
  right: 25%;
  display: none;
}
  .title-child.active{
    display: block;
  }
</style>
