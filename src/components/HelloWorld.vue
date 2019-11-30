<template>
  <div class="hello">
    <div class="all-all-num" v-for="(each, num) in aniNum" :key="num">
      <div class="all-each-view">
        <div class="all-each-all">
          <div
            class="all-each-num"
            v-for="(item, index) in [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]"
            :key="index"
          >
            {{ item }}
          </div>
        </div>
      </div>
      <div class="comma">,</div>
    </div>
    <button @click="getNum">ceshi</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    realNum: {
      type: Array,
      default: () => []
    },
    clientWidth: {
      type: Number,
      default: 1990
    }
  },
  data() {
    return {
      scrollHight: 40,
      aniNum: [0, 6, 0, 0, 3, 4, 0]
    };
  },
  methods: {
    getAnimate() {
      this.aniNum.forEach((item, index) => {
        document.getElementsByClassName("all-each-all")[
          index
        ].style.transform = `translateY(-${this.scrollHight * item}px)`;
        document.getElementsByClassName("all-each-all")[
          index
        ].style.transition = "all 1s";
      });
    },
    getNum() {
      this.aniNum = [0, 2, 9, 7, 3, 4, 0];
      this.$nextTick(() => {
        this.getAnimate();
      });
    }
  },
  mounted() {
    if (this.clientWidth <= 1440) {
      this.scrollHight = 20;
    }
    this.aniNum = this.realNum;
    this.getAnimate();
  },
  watch: {
    clientWidth(val) {
      if (val <= 1440) {
        this.scrollHight = 20;
        this.$nextTick(() => {
          this.getAnimate();
        });
      } else {
        this.scrollHight = 40;
        this.$nextTick(() => {
          this.getAnimate();
        });
      }
    }
  }
};
</script>

<style lang="less">
@viewwidth: 40px;
@viewHeight: 40px;
@fontSize: 36px;
.hello {
  display: flex;
  .all-all-num {
    display: flex;
    line-height: @viewHeight;
    font-size: @fontSize;
    .all-each-view {
      width: @viewwidth;
      height: @viewHeight;
      overflow: hidden;
      .all-each-num {
        width: 100%;
        height: 100%;
      }
    }
  }
}
@media screen and (max-width: 1440px) {
  // @viewwidth:20px;
  // @viewHeight:20px;
  // @fontSize:18px;
  .hello {
    display: flex;
    .all-all-num {
      display: flex;
      line-height: 20px;
      font-size: 18px;
      .all-each-view {
        width: 20px;
        height: 20px;
        overflow: hidden;
        .all-each-num {
          width: 100%;
          height: 100%;
        }
      }
    }
  }
}
</style>
