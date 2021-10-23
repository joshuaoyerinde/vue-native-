<template>
  <app-navigator></app-navigator>
</template>
<script>
import {
  createAppContainer,
  createStackNavigator
} from "vue-native-router";
import MainScreen from './component/Main.vue'
import TestScreen from './component/Test.vue'
// import HomeScreen from "./screens/HomeScreen.vue";
// import DetailsScreen from "./screens/DetailsScreen.vue";
const StackNavigator = createStackNavigator(
  {
    Main: MainScreen,
    Test: TestScreen
  },
  {
    initialRouteName: 'Main'
  }
);
const AppNavigator = createAppContainer(StackNavigator);
export default {
  components: { AppNavigator }
}
</script>