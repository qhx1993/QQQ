<template>
    <div>
        <el-row type="flex" justify="space-between">
            <el-col :span="3">
                <a class="logo" href="#"></a>
            </el-col>
            <el-col :span="12">
                <ul class="main-menu">
                    <li><a @mouseover="dlMenuShow()" @mouseout="isDLMeuHide = true" href="#">深度学习Demo</a></li>
                    <li><a @mouseover="webMenuShow()" @mouseout="isWebMeuHide = true" href="#">前端Demo</a></li>
                </ul>
            </el-col>
            <el-col :span="4">
                <a @click="msg" class="reserve box foo">社交媒体</a>
                <router-link to="/" class="reserve box foo">控制台</router-link>
            </el-col>
        </el-row>
        <div class="sub-menu">
            <div :class="{ 'sub-menu-hide': isDLMeuHide }">
                <ul>
                    <li><router-link to="/">Style Transfer</router-link></li>
                    <li><router-link to="/">Image Super Resolution</router-link></li>
                </ul>
            </div>
            <div :class="{ 'sub-menu-hide': isWebMeuHide }">
                <ul>
                    <li><router-link to="/">Demo 1</router-link></li>
                    <li><router-link to="/">Demo 2</router-link></li>
                </ul>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
      name: "AppHeader",
      data() {
        return {
          isDLMeuHide: true,
          isWebMeuHide: true
        }
      },
      methods: {
        msg: function () {
          alert("社交媒体");
        },
        dlMenuShow: function () {
          this.isDLMeuHide = false;
          this.isWebMeuHide = true;
        },
        webMenuShow: function () {
          this.isWebMeuHide = false;
          this.isDLMeuHide = true;
        },
      }
    }
</script>

<style>
    .logo {
        height: 22px;
        width: 87px;
        background: url("../assets/logo.png") center no-repeat;
        display: block;
    }
    .el-row {
        height: 60px;
        display: flex;
        align-items: center;
        background: #f8f8f8;
        box-shadow: 0 1px 8px 0 rgba(0, 0, 0, 0.1);
    }
    .el-col {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .box {
        position: relative;
        vertical-align: middle;
        display: inline-block;
        transition: 0.5s;
        cursor: pointer;
    }
    .box:hover {
        border: 1px solid rgba(0, 160, 80, 0);
    }
    .box::before, .box::after {
        width: 100%;
        height: 100%;
        z-index: 3;
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;
        -webkit-transform: scale(0);
        -moz-transform: scale(0);
        -ms-transform: scale(0);
        -o-transform: scale(0);
        transform: scale(0);
        transition: 0.5s;
    }
    .box:hover:before, .box:hover:after {
        -webkit-transform: scale(1);
        -moz-transform: scale(1);
        -ms-transform: scale(1);
        -o-transform: scale(1);
        transform: scale(1);
    }
    .reserve {
        padding: 10px;
        border: 1px solid #7a7977 !important;
    }
    a {
        font-size: 12px;
        font-family: "Facto", "Hiragino Sans GB", "Microsoft YaHei", "WenQuanYi Micro Hei", sans-serif;
        font-weight: 600;
        line-height: 0.86;
        letter-spacing: 0.5px;
        margin-right: 5px;
        text-decoration: none;
        outline: none;
        color: #7A7977;
    }
    .foo:before {
        border-bottom: 1px solid rgba(122, 121, 119, 0.8);
        border-left: 1px solid rgba(122, 121, 119, 0.8);
        -webkit-transform-origin: 0% 100%;
        -moz-transform-origin: 0% 100%;
        -ms-transform-origin: 0% 100%;
        -o-transform-origin: 0% 100%;
        transform-origin: 0% 100%;
    }
    .foo:after {
        border-top: 1px solid rgba(122, 121, 119, 0.8);
        border-right: 1px solid rgba(122, 121, 119, 0.8);
        -webkit-transform-origin: 100% 0%;
        -moz-transform-origin: 100% 0%;
        -ms-transform-origin: 100% 0%;
        -o-transform-origin: 100% 0%;
        transform-origin: 100% 0%;
    }
    li {
        float: left;
        list-style: none;
        padding: 12px 20px;
    }
    li a {
        font-size: 12px;
    }
    li a:hover {
        color: #333333;
        opacity: 0.5;
    }
    .sub-menu {
        position: absolute;
        width: 100%;
    }
    .sub-menu div {
        position: absolute;
        width: 100%;
        left: 0;
        background-color: #F7F7F7;
        transition: all 0.2s;
        box-shadow: 0 3px 8px 0 rgba(0, 0, 0, 0.1);
    }
    .sub-menu div:hover {
        visibility: visible;
    }
    .sub-menu ul {
        line-height: 0px;
        margin: 0px;
    }
    .sub-menu-hide {
        visibility: hidden;
    }
</style>
