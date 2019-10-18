<template lang="html">
  <div class="liconInput">
    <div class="inputWrapper">
      <div class='iconBox'>
        <div :class="iconName" :style="iconStyle">
        </div>
      </div>
      <input :type="type || 'text'" :placeholder="placeholder" v-model="value" @blur="sendData">
    </div>
  </div>
</template>

<script>
export default {
  created() {
    console.log(this.type);
  },
  props:['iconName', 'iconStyle', 'title', 'placeholder', 'type'],
  data() {
    return {
      value: ''
    }
  },
  methods: {
    sendData() {
      var _this = this;
      this.$emit('getValue', {name: _this.title, value: _this.value});
    }
  }
}
</script>

<style lang="scss" scoped>
.inputWrapper{
  height:40px;
  display: flex;
  align-items: center;
  input{
    background:transparent;
    flex:1;
    outline:none;
    border:none;
    color:#666;
    font:normal 14px/40px '微软雅黑';
    padding-left: 10px;
  }
}
.iconBox{
  display: flex;
  align-items: center;
  justify-content: center;
  width:50px;
  height:50px;
}
.liconInput{
  margin-top: 20px;
  border-radius: 6px;
  border:1px solid #999;
}
</style>
