<template>
  <div class="pc">
    <h1>{{ msg }}</h1>
    <div
      class="demo"
      @mouseover="mouseOver"
      @mouseleave="mouseLeave"
      :style="active"
    >
      <p ref="acp">我是内容</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: "HelloWorld,I am PC",
      active: "",
    };
  },
  methods: {
    // 移入
    mouseOver() {
      this.active = "background-color:black";
      // 操作dom 获取p标签改变其样式
      var acps = this.$refs.acp
      acps.style.color = "red"
    },
    // 移出
    mouseLeave() {
      this.active = "";
      this.$refs.acp.style=''
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
.pc {
  .demo {
    width: 100%;
    height: 300px;
    background-color: lightcoral;
    p {
      color: limegreen;
    }
  }
}
</style>

