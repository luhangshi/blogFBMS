<template>
  <div class="main df jac">
    <div class="loginContainer fc6">
      <transition name="left">
        <div v-if="login" class="loginArea">
          <h3 class="f26">欢迎登录</h3>
          <div class="form">
            <iconInput v-for="(item, i) in inputParams"
            :key="i"
            :iconName="item.iconName"
            :iconStyle="item.iconStyle"
            :title="item.title"
            :placeholder="item.placeholder"
            :type="item.type"
            @getValue="getValue"/>
          </div>
        </div>
        <div v-else class="regArea">

        </div>
      </transition>
    </div>
  </div>
</template>

<script>
const iconInput = ()=> import('@/utils/liconInput');
export default {
  created() {

  },

  data() {
    return {
      login: true,
      params: {
        username: '',
        password: ''
      },
      inputParams: [
        {iconName: 'iconfont iconyonghu f22', iconStyle: '', placeholder: '请输入用户的密码', title: 'username'},
        {iconName: 'iconfont iconmima f20', iconStyle: '', placeholder: '请输入用户的密码', title: 'password', type:'password'}
      ]
    }
  },

  methods:{
    getValue(data) {
      console.log(`接收到参数:${data.name} => ${data.value}`);
    }
  },
  components: {
    iconInput
  },

  computed: {
    transitionName:function() {
      if(!this.login) return 'to-right';
      return 'to-left'
    }
  }
}
</script>

<style lang="scss" scoped>
.main{
  background-image: url('./../assets/loginbg.png');
  background-size: 1920px 1080px;
  background-position: center;
  background-repeat: no-repeat;
  width:100vw;
  height:100vh;
  filter:brightness(.9);
}
.loginContainer{
  width:450px;
  background-color: rgba(255, 255, 255, .8);
  border-radius: 14px;
  animation: loginAni .2s ease-out 1 forwards;
  opacity: 0;
  position: relative;
  height:500px;
  box-sizing: border-box;
  padding:0 40px;
  &>div{
    height:500px;
    position: absolute;
    top:0;
  }
  h3{
    font-weight: 500;
    text-align: center;
    margin-top: 60px;
    line-height: 30px;
  }
}
.loginArea{
  width: 370px;
}
.form{
  height: 350px;
  margin-top: 60px;
}
@keyframes loginAni{
  0{
    transform:translateY(0)
  }
  100%{
    opacity: 1;
    transform: translateY(-20%);
    box-shadow: 0 0 10px  #ccc;
  }
}
</style>
