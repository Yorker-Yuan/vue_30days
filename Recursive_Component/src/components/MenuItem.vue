<template>
  <li class="item">
    <span v-if="hasChild" @click="toggleOpen">{{opened ? '-' : '+'}}</span> <!--切換不頻繁用v-if =>直接動用DOM元素 ，處理較繁複-->
    <a href="javascript:;">{{item.label}}</a>
     <ul v-show="hasChild && opened">  <!--切換頻繁用v-show =>利用css處理顯示隱藏 ，較有效率-->
      <MenuItem v-for="(child,index) in item.children" :key="index" :item="child"/>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'MenuItem',
  props:{
    item:{
      type:Object,
      required:true //代表:必填欄位
    }
  },
  data(){
    return{
      opened:false
    };
  },
  computed:{
    hasChild(){
      return this.item.children && this.item.children.length ? true : false;
    }
  },
  methods:{
    toggleOpen(){
      if(this.hasChild){
        this.opened = !this.opened;
      }
    }
  }
}
</script>