<template>
  <div id="allNumCon" class="allNumCon">
    <div v-for="item in list" :key="'number' + item">
      <div class="OneNumCon">
        <div :class="'rolling_' + dataNumStr[item - 1]" :style="{'transform': 'translate3d(0,-' + 30 * numStr[item - 1] + 'px, 0)'}" class="OneListNum">
          <!-- <div><img :src="require('../../assets/image/index/0.png')" alt=""></div> -->
          <div>0</div>
          <div v-for="num in [1,2,3,4,5,6,7,8,9,0]" :key="num">
            num
            <!-- <img :src="require('../../assets/image/index/'+(num)+'.png')" alt=""> -->
            </div>
        </div>
      </div><div v-if="(list - item) % 3 === 0 && (list - item) !== 0" class="OneNumCon_dou">
        <!-- <img :src="require('../../assets/image/index/point.png')" alt=""> -->
        ,
        </div>
    </div>
  </div>
  <div v-else id="allNumCon" class="allNumCon">
    <!-- <img :src="require('../../assets/image/index/0.png')" alt=""> -->
    ,
    </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
