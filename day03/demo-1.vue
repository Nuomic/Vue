<template>
  <div class="container">
    hello world
    <ul>
      <li
        v-for="(item, index) in list"
        @click="choose(index)"
        :class="{active:index ==current}"
        :key="index"
      >{{item}}
      </li>
    </ul>
    <button @click="add()">添加</button>
<ul>
    <li v-for="(item, index) in target"
        :key="index">{{item}}</li>
</ul>
    </div>
</template>

<script>
export default {
  name: 'demo1',
  data() {
    return {
      list: [1, 2, 3, 4, 5, 6, 7],
      current:"",
      target:[]
    }
  },
  methods: {
      choose(index){
          this.current = index
      },
      add(){
          this.target.push(this.list[this.current])
      }
  },
  components: {}
}
</script>

<style scoped>
li.active{
    background-color: green;
}
</style>
