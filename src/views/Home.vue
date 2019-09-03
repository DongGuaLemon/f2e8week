<template>
  <div class="home">
    <div class="navlogo">
      <div>
        <img src="../assets/logo.svg" />
      </div>
      <div class="progressbar">
        <div>
          <span>{{value}}GB</span>
          <span class="endprog">100GB</span>
          <b-progress :value="value" :max="max" class="mb-3"></b-progress>
        </div>
        <div>
          <b-input-group>
            <b-input-group-text slot="prepend" style="background-color:#556F96;"><img src="../assets/baseline_search_white_24dp.png"></b-input-group-text>
            <b-form-input></b-form-input>
            <b-dropdown slot="append">
              <b-dropdown-item>Action A</b-dropdown-item>
              <b-dropdown-item>Action B</b-dropdown-item>
            </b-dropdown>
          </b-input-group>
        </div>
      </div>
    </div>
    <div class="main">
      <div class="tab">
        <tabs />
      </div>
      <div class="tabcontent">
        <tableside/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import tabs from "@/components/tabs.vue";
import tableside from '@/components/tableside.vue'
export default {
  name: "home",
  data() {
    return {
      value: 30,
      max: 100
    };
  },
  components: {
    tabs,
    tableside
  },
  mounted() {
    let v = document.querySelector(".tab");
    console.log(v.clientHeight);
    console.log(v.offsetTop);
    console.log(v.offsetLeft);
  }
};
</script>
<style>
.home {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}
.navlogo {
  width: 70%;
  display: flex;
  justify-content: space-around;
  margin-top: 15px;
}
.progress-bar {
  background-color: #556f96 !important;
}
.progressbar {
  width: 60%;
  position: relative;
}
.endprog {
  position: absolute;
  right: 0;
}
.main {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
.tab {
  width: 65%;
}
.tabcontent {
  width: 18%;
  height: 547px;
  background-color: white;
  position: relative;
  top: 25px;
  border: 1px solid #ffffff;
  border-radius: 10px;
}
</style>
