<template>
  <view class="container">
     <status-bar background-color="rgba(255, 0, 0, 0.192)" bar-style="light-content" 
      />
    <text class="header">The Github Users</text>
    <scroll-view :style="{width:300}">
      <view class="border" v-for="(user,i) in users" :key="i"> 
        <touchable-opacity class="flex-container" @press="handleClick(user)">
          <image
          :style="{width: 60, height: 60,borderRadius:100}"
          :source="{uri: user.avatar_url}"
          />
          <!-- <text class="text-title">{{ user.title }}</text> -->
          <text class="text-title">{{ user.contributions }}<text>contributions</text></text>
        </touchable-opacity>
      <!-- <TestUser/> -->
      </view>
    </scroll-view>
    <!-- <text class="text-color-primary">Test Vue Native</text>
    <view class="container2">
      <button :title="title" @press="onClickButton"/>
      <text class="text-color-primary">{{count}}</text> -->
    <!-- </view> -->
  </view>
</template> 
<script>
// import TestUser from './component/Test.vue';
// import { Alert } from 'react-native';

// import './assets/style.css';
// import style from "app.json";
export default {
  data:()=>({
    title:"Click Button",
    count: 0,
    users:[]

  }), 
  props: {
    navigation: {
      type: Object
    }
  },
  async created() {
    // const url = 'https://api.github.com/repos/GeekyAnts/vue-native-core/contributors'
    const url = "https://jsonplaceholder.typicode.com/photos";
    this.users = await fetch(url).then(res => res.json())
    // console.log(this.users);
  },
  // async mounted(){
  //   const url = "https://jsonplaceholder.typicode.com/photos";
  //    this.users = await fetch(url).then(res => res.json())
     
  // },
  methods:{
    onClickButton(){
      this.count = this.count + 1;
      if(this.count == 8){
        // console.log('welcome');
        // Alert.alert("you're welcome")
        // alert("you are good now omo mi ride on");
      }else if(this.count == 35){
        alert("Alaye You're getting old ooo")
      }else if(this.count == 100){
        alert("You're Doing well Go to heaven");
        console.log('welcome');
      }
    },
    handleClick(user){
      console.log(user.data);
      this.navigation.navigate("Test",{imagesrc:user.data.thumbnail});
      // alert("joshua");
    }
  },
}
</script>

<style src="assets/style.css" lang="css">
.container {
    background-color: white;
    align-items: center;
    justify-content: center;
    flex: 1;
    background-color: rgba(255, 0, 0, 0.192);
    /* margin-top: 33px; */
  }
  .header{
    /* margin-top: 40px; */
    font-size: 30px;
    color:#F9682F;
    font-weight: 700;
    letter-spacing: 1.5px;
    
  }
  .border{
    border-bottom-width:1;
    border-top-width: 1;
    border-bottom-color: green;
    border-color: grey;
    width: 100%;
    padding: 2px, 5px, 2px;
    top:20px
  }
  .flex-container{
    flex-direction: row;
    align-items: center;
    padding: 2px;
  }
  .text-title{
    left:4px;
    font-size:12px;
    width: 100%;
    overflow: scroll;
     /* text-align: center; */
  }
  image{
    border-radius: 100px;
  }
</style>
