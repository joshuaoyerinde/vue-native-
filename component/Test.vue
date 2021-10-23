<template>
    <view class="con">
        <text>
            <image
            :style="{width: 300, height: 300,borderRadius:100}"
            :source="{uri: navigation.getParam('imagesrc')}"
          />
        </text>
    </view>
</template>
<script>
export default {
    data:()=>({

    }),
    props: {
    navigation: {
      type: Object
    }
  },
}
</script>
<style scoped src="./assets/style.css">

</style>
