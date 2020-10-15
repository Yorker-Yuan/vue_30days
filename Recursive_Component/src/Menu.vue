<template>
  <div id="app">
    <ul class="menu">
      <MenuItem :item="menuList" />
    </ul>
  </div>
</template>

<script>
import MenuItem from "./components/MenuItem";

export default {
  components:{
    MenuItem
  },
  data() {
    return {
      menuList: {
        label: "24h購物(2056)",
        children: [
          {
            label: "電玩/遊戲(552)",
            children: [
              {
                label: "PS4 遊戲(127)",
              },
              {
                label: "Switch 遊戲(63)",
              },
            ],
          },
          {
            label: "積木桌遊(495)",
            children: [
              {
                label: "德國HABA桌遊(88)",
              },
              {
                label: "趣味桌遊/玩具(81)",
              },
            ],
          },
        ],
      },
    };
  },
};
</script>

<style>
  ul{
    list-style:none;
  }
  .item>span{
    display:inline-block;
    width:20px;
    height:20px;
    text-align:center;
    background-color:#eee;
    border:1px solid #000;
    box-sizing:border-box;
    margin:5px;
  }
</style>
