<template>
  <div class="tabscomponent">
    <b-card no-body>
      <b-tabs card>
        <b-tab title="我的抽屜" active>
          <b-card-text>
            <tabstable />
          </b-card-text>
        </b-tab>
        <b-tab title="共用抽屜">
          <b-card-text>Tab Contents 2</b-card-text>
        </b-tab>
        <b-tab title="重要抽屜">
          <b-card-text>Tab Contents 3</b-card-text>
        </b-tab>
        <b-tab title="垃圾桶">
          <b-card-text>Tab Contents 4</b-card-text>
        </b-tab>
      </b-tabs>
      <div class="plusfolder">
        <div class="newfolder">
          <img src="../assets/plus.svg" />
          <span>新增資料夾</span>
        </div>
        <div class="newdoc">
          <img src="../assets/plus.svg" />
          <span>新增檔案</span>
        </div>
      </div>
    </b-card>
  </div>
</template>
<script>
import tabstable from "./tabstable.vue";
export default {
  components: {
    tabstable
  }
};
</script>
<style>
.tabscomponent {
  height: 100%;
}
.card {
  height: 600px;
  border: unset !important;
  border: 1px solid #ffffff;
  border-radius: 10px !important;
  position: relative;
}
.card-header {
  padding-left: 0 !important;
}
.nav-tabs .nav-item {
  background-color: #556f96;
  width: 150px;
  text-align: center;
  margin-left: 10px;
  border-top-left-radius: 5px;
  border-top-right-radius: 5px;
}
.tabscomponent a {
  color: white;
}
.tabscomponent a:hover {
  text-decoration: unset;
  color: white;
}
.plusfolder {
    width: 500px;
  display: flex;
  position: absolute;
  bottom: 5%;
  left: 5%;
}
.newfolder span{
    padding-left: 15px;
}
.newdoc{
    padding-left: 15%;
}
.newdoc span{
    padding-left: 15px;
}
</style>