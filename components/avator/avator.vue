<template>
	<view class="cc-avatar" :style="{
	        width: avatarWidth + 'px',
	        height: avatarHeight + 'px',
	        borderRadius: round ? '100%' : '0',
	      }">
		<img :mode="imgMode" @error="handleError" v-if="src && !error" :style="{ borderRadius: round ? '100%' : '5px' }"
			class="cc-avatar-img" :src="src" />
		<slot v-else></slot>
	</view>
</template>

<script lang="ts">
	import {
		defineComponent
	}
	from "vue";
	export default defineComponent({
		setup() {
			return {
				title: "hello",
				error: false,
				size: '60',
				round: true,
				imgMode: 'aspectFill',
				avatarWidth: 60,
				avatarHeight: 60,
				src: "https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png",
			};
		},
	});
</script>

<style lang="scss">
.content {
  text-align: center;
  height: 400upx;
}

.logo {
  height: 200upx;
  width: 200upx;
  margin-top: 200upx;
}

.title {
  font-size: 36upx;
  color: #8f8f94;
}
.cc-avatar {
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 14px;
  color: #fff;
  background: #c0c4cc;
  &-img {
    width: 100%;
    height: 100%;
  }
}
</style>
