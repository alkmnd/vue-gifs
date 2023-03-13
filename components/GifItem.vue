<template>
  <view class="container">
    <image class="img" :source="{uri: `${gif.images.original.url}`}" style="max-width:100%;"/>
    <text class="title">{{titleCase(gif.title)}}</text>
  </view>
</template>
<script>
export default {
  name: "GifItem",
  props: ["gif"],
  methods: {
    titleCase(text) {
      const textArray = text.split(" ");
      return textArray
        .map(text => {
          const trimmedText = text.trim();
          return `${trimmedText[0].toUpperCase()}${trimmedText.slice(1)}`;
        })
        .join(" ");
    }
  }
};
</script>
<style>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 30px;
  position: relative;
}
.img {
  height: 200px;
  width: 300px;
}
.title {
  font-size: 14px;
  font-weight: 500;
  margin-top: 7px;
}
</style>