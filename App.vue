<template>
  <view>
      <scroll-view class="scroll-view">
          <gif-item v-for="gif in gifs" :gif="gif" :key="gif.id" v-if="!loading"/>
          <view class="loading-container" :style="{flex: 1, justifyContent: 'center'}" v-if="loading">
              <activity-indicator size="large" color="#0000ff"></activity-indicator>
          </view>
      </scroll-view>
  </view>
</template>
<script>
import Giphy from 'giphy-js-sdk-core';
const client = Giphy('TxuQbNU1nyDBwpqrcib61LxmOzsXTPEk');
import GifItem from './components/GifItem';
import Header from './components/header';
import {SafeAreaView} from 'react-native';

export default {
  name: 'App',
  data() {
    return {
      gifs: [],
      loading: true
    };
  },
  async created() {
    const response = await client.trending('gifs', {limit: 20});
    this.gifs = response.data;
    this.loading = false;
  },
  components: {GifItem, Header}
};
</script>
<style>
  .scroll-view {
      padding-top: 100px;
      padding-bottom: 30px;
  }
  .loading-container {
      height: 600px;
  }
</style>
