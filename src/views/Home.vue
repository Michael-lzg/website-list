<template>
  <div class="container">
    <div class="list">
      <div class="block" v-for="(block,k) in list" :key="k">
        <div class="title">{{block.title}}</div>
        <div class="listItem">
          <div class="items" v-for="(item,index) in block.list" :key="index" v-on:mouseover="changeActive($event)" v-on:mouseout="removeActive($event)">{{item.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import list from '../data/netList'
console.log(list)
export default {
  data () {
    return {
      list: list
    }
  },
  methods: {
    changeActive ($event) {
      $event.target.classList.add('active')
    },
    removeActive ($event) {
      $event.target.classList.remove('active')
    }
  }
}
</script>

<style lang="less" scoped>
.container {
  width: 1200px;
  margin: 0 auto;
  background-color: #fff;
}
.list {
  .block {
    margin-top: 15px;
  }
  .title {
    font-size: 18px;
    font-weight: 700;
    line-height: 30px;
  }
  .listItem {
    margin-top: 5px;
  }
  .items {
    display: inline-block;
    width: 238px;
    height: 45px;
    line-height: 45px;
    background: rgba(230, 247, 255, 0.96);
    text-align: center;
    margin-right: 2px;
    margin-top: 2px;
    cursor: pointer;
    font-size: 12px;
    transition: all 0.2s;
    border-radius: 2px;
  }
  .active {
    font-size: 16px;
    font-weight: 600;
    color: #fff;
    background: linear-gradient(90deg, #1890ff, #455bfb);
  }
}
</style>
