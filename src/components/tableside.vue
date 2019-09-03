<template>
  <div class="tableside">
    <h3>HELLO</h3>
    <div class="tablecontent">
      <div class="content">
        <span>修改日期</span>
        <span class="contentend">2019.09.02 10:00</span>
      </div>
      <div class="content">
        <span>類型</span>
        <span class="contentend">資料夾</span>
      </div>
      <div class="content">
        <span>擁有人</span>
        <span class="contentend">her224</span>
      </div>
      <div class="content">
        <span>大小</span>
        <span class="contentend">5.8 gb</span>
      </div>
    </div>
    <div class="kindsvg">
      <div class="kindtitle">
        <span>預覽內容</span>
      </div>
      <div class="kindcontent">
        <ul>
          <li v-for="(item,index) in list" :key="index">
            <img :src="require(`../assets/${item.type}.svg`)" width="20px" />
            <span>{{item.name}}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      list: [
        { type: "Video", name: "Video" },
        { type: "Picture", name: "Picture" },
        { type: "File", name: "File" }
      ]
    };
  }
};
</script>
<style>
.tableside {
  width: 100%;
  padding-left: 20px;
  padding-right: 20px;
  padding-top: 10%;
}
.tableside h3 {
  padding-left: 10px;
}
.tablecontent {
  display: flex;
  flex-direction: column;
  border-top-style: solid;
  border-bottom-style: solid;
  border-bottom-color: #f5f5f5;
  border-top-color: #f5f5f5;
  border-top-width: 1px;
  border-bottom-width: 1px;
}
.content {
  position: relative;
  padding-left: 10px;
  padding-top: 5px;
}
.contentend {
  position: absolute;
  right: 10px;
}
.kindsvg {
  width: 100%;
}
.kindtitle{
    margin-top: 10px;
}
.kindtitle span {
  padding-left: 10px;
}
.kindcontent ul {
  list-style: none;
  padding: 0;
  padding-left: 10px;
}
.kindcontent li {
  padding-top: 10px;
  display: flex;
}
.kindcontent span {
  padding-left: 20%;
}
.kindcontent img {
  vertical-align: middle;
}
</style>