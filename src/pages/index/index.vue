<template>
	<view class="content">
        <image class="logo" src="../../static/logo.png"></image>
		<view>
            <text class="title">{{title}}</text>
            <button type="primary" @tap="this.getUserOpne()"> 获取openId</button>
        </view>
	</view>
</template>

<script lang="ts">
    import Vue from 'vue';
    import {Component} from "vue-property-decorator";
    import {
        namespace
    } from "vuex-class";

    const initModule=namespace('init')
    @Component({})
    class Index extends  Vue {
        @initModule.State(state => state.hasLogin) public hasLogin!: boolean;
        @initModule.Action('getUserOpenId') getUserOpenId!: Function;

        title= 'Hello';

        onLoad() {
            console.log('onLoad')
        }

        async getUserOpne(){
            const openId=await this.getUserOpenId();
            console.log(openId,this.hasLogin);
        }
    }

    export default Index;
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}
    .logo{
        height: 200upx;
        width: 200upx;
        margin-top: 200upx;
    }
	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
