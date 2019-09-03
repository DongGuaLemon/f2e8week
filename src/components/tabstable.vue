<template>
  <div class="tabstable">
    <table>
      <tr class="headers">
        <th><img src="../assets/bookmark.svg" /></th>
        <th><b-form-checkbox class="mr-n2"></b-form-checkbox></th>
        <th>名稱<img :src="require(`../assets/down-arrow.svg`)"></th>
        <th>修改日期<img :src="require(`../assets/down-arrow.svg`)" ></th>
        <th>類型<img :src="require(`../assets/down-arrow.svg`)"></th>
        <th>擁有人<img :src="require(`../assets/down-arrow.svg`)"></th>
        <th>大小<img :src="require(`../assets/down-arrow.svg`)"></th>
        <th></th>
      </tr>
      <tr v-for="(item,index) in list" :key="index" @click="select(index)" :class="{focustyle:item.selected||item.check}">
        <td><img src="../assets/bookmark.svg" /></td>
        <td><b-form-checkbox class="mr-n2" v-model="item.check"></b-form-checkbox></td>
        <td><img :src="require(`../assets/${item.src}.svg`)" class="namepic"><span>{{item.name}}</span></td>
        <td>{{item.date}}</td>
        <td>{{item.type}}</td>
        <td>{{item.user}}</td>
        <td>{{item.size}}</td>
        <td><img src="../assets/menu.svg"></td>
      </tr>
    </table>
  </div>
</template>
<script>
export default {
    data() {
        return {
            list:[
                {mark:false,check:false,src:'folder',name:'HELLO',date:'2019.09.09 10:00',type:'資料夾',user:'her224',size:'5.4'},
                {mark:false,check:false,src:'folder',name:'HELLO',date:'2019.09.09 10:00',type:'資料夾',user:'her224',size:'5.4'},
                {mark:false,check:false,src:'folder',name:'HELLO',date:'2019.09.09 10:00',type:'資料夾',user:'her224',size:'5.4'},
                {mark:false,check:false,src:'Picture',name:'HELLO',date:'2019.09.09 10:00',type:'照片',user:'her224',size:'5.4'},
                {mark:false,check:false,src:'Picture',name:'HELLO',date:'2019.09.09 10:00',type:'照片',user:'her224',size:'5.4'},
            ],
        }
    },
    methods:{
        select(index){
           for(let i in this.list){
               if(i==index){
                   this.list[i].selected=!this.list[i].selected
               }
               else{
                   this.list[i].selected=false
               }
           }
        }
    },
    created(){
        for(let i in this.list){
            //直接加入實體未產生所以無法操控值需用set新增實體
            //this.list[i].selected=false
            this.$set(this.list[i], 'selected',false)
        }
    }
};
</script>
<style>
.tabstable{
    width: 100%;
    max-height: 400px;
    overflow: auto;
    overflow-x: hidden;
}
.tabstable table{
    width: 100%;
}
.headers{
    border-bottom-style:solid;
    border-width: 1px;
    border-bottom-color:#F5F5F5; 
}
.tabstable tr td{
    padding-top: 10px;
}
.namepic{
    vertical-align:middle;
    padding-right: 10px;
}
.focustyle{
    background-color: #F5F5F5;
}
</style>