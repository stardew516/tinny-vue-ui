<template>
  <div class="grid-container" :style="{'grid-template-rows': 100/rows + '%'}">
    <slot></slot>
  </div>
</template>
<script>
  export default {
    props: {
      rows: {
        type: [Number, String],
        twoWay: true,
        default: 3
      },
      cols: {
        type: [Number, String],
        twoWay: true,
        default: 3
      }
    },
    data () {
      return {
      }
    },
    watch: {
    },
    methods: {
    }
  }
</script>
<style lang="scss" scoped>
  @import "../static/iconfont.scss";
  .grid-container {
    display: grid;
    /* grid-template-columns: 80px; */
    /* grid-template-rows: 25%; */
    grid-gap: 1px;
    .grid-items {
      overflow: hidden;
    }
    .grid-items11 {
      grid-row: 1;
      grid-column: 1;
    }
    .grid-items12 {
      grid-row: 1;
      grid-column: 2;
    }
    .grid-items13 {
      grid-row: 1;
      grid-column: 3;
    }
    .grid-items14 {
      grid-row: 1;
      grid-column: 4;
    }
    .grid-items15 {
      grid-row: 1;
      grid-column: 5;
    }
    .grid-items16 {
      grid-row: 1;
      grid-column: 6;
    }
    .grid-items17 {
      grid-row: 1;
      grid-column: 7;
    }
    .grid-items18 {
      grid-row: 1;
      grid-column: 8;
    }
    .grid-items19 {
      grid-row: 1;
      grid-column: 9;
    }
    .grid-items110 {
      grid-row: 1;
      grid-column: 10;
    }
    .grid-items21 {
      grid-row: 2;
      grid-column: 1;
    }
    .grid-items22 {
      grid-row: 2;
      grid-column: 2;
    }
    .grid-items23 {
      grid-row: 2;
      grid-column: 3;
    }
    .grid-items24 {
      grid-row: 2;
      grid-column: 4;
    }
    .grid-items25 {
      grid-row: 2;
      grid-column: 5;
    }
    .grid-items26 {
      grid-row: 2;
      grid-column: 6;
    }
    .grid-items27 {
      grid-row: 2;
      grid-column: 7;
    }
    .grid-items28 {
      grid-row: 2;
      grid-column: 8;
    }
    .grid-items29 {
      grid-row: 2;
      grid-column: 9;
    }
    .grid-items210 {
      grid-row: 2;
      grid-column: 10;
    }
    .grid-items31 {
      grid-row: 3;
      grid-column: 1;
    }
    .grid-items32 {
      grid-row: 3;
      grid-column: 2;
    }
    .grid-items33 {
      grid-row: 3;
      grid-column: 3;
    }
    .grid-items34 {
      grid-row: 3;
      grid-column: 4;
    }
    .grid-items35 {
      grid-row: 3;
      grid-column: 5;
    }
    .grid-items36 {
      grid-row: 3;
      grid-column: 6;
    }
    .grid-items37 {
      grid-row: 3;
      grid-column: 7;
    }
    .grid-items38 {
      grid-row: 3;
      grid-column: 8;
    }
    .grid-items39 {
      grid-row: 3;
      grid-column: 9;
    }
    .grid-items310 {
      grid-row: 3;
      grid-column: 10;
    }
    .grid-items41 {
      grid-row: 4;
      grid-column: 1;
    }
    .grid-items42 {
      grid-row: 4;
      grid-column: 2;
    }
    .grid-items43 {
      grid-row: 4;
      grid-column: 3;
    }
    .grid-items44 {
      grid-row: 4;
      grid-column: 4;
    }
    .grid-items45 {
      grid-row: 4;
      grid-column: 5;
    }
    .grid-items46 {
      grid-row: 4;
      grid-column: 6;
    }
    .grid-items47 {
      grid-row: 4;
      grid-column: 7;
    }
    .grid-items48 {
      grid-row: 4;
      grid-column: 8;
    }
    .grid-items49 {
      grid-row: 4;
      grid-column: 9;
    }
    .grid-items410 {
      grid-row: 4;
      grid-column: 10;
    }
    .grid-items51 {
      grid-row: 5;
      grid-column: 1;
    }
    .grid-items52 {
      grid-row: 5;
      grid-column: 2;
    }
    .grid-items53 {
      grid-row: 5;
      grid-column: 3;
    }
    .grid-items54 {
      grid-row: 5;
      grid-column: 4;
    }
    .grid-items55 {
      grid-row: 5;
      grid-column: 5;
    }
    .grid-items56 {
      grid-row: 5;
      grid-column: 6;
    }
    .grid-items57 {
      grid-row: 5;
      grid-column: 7;
    }
    .grid-items58 {
      grid-row: 5;
      grid-column: 8;
    }
    .grid-items59 {
      grid-row: 5;
      grid-column: 9;
    }
    .grid-items510 {
      grid-row: 5;
      grid-column: 10;
    }
    .grid-items61 {
      grid-row: 6;
      grid-column: 1;
    }
    .grid-items62 {
      grid-row: 6;
      grid-column: 2;
    }
    .grid-items63 {
      grid-row: 6;
      grid-column: 3;
    }
    .grid-items64 {
      grid-row: 6;
      grid-column: 4;
    }
    .grid-items65 {
      grid-row: 6;
      grid-column: 5;
    }
    .grid-items66 {
      grid-row: 6;
      grid-column: 6;
    }
    .grid-items67 {
      grid-row: 6;
      grid-column: 7;
    }
    .grid-items68 {
      grid-row: 6;
      grid-column: 8;
    }
    .grid-items69 {
      grid-row: 6;
      grid-column: 9;
    }
    .grid-items610 {
      grid-row: 6;
      grid-column: 10;
    }
    .grid-items71 {
      grid-row: 7;
      grid-column: 1;
    }
    .grid-items72 {
      grid-row: 7;
      grid-column: 2;
    }
    .grid-items73 {
      grid-row: 7;
      grid-column: 3;
    }
    .grid-items74 {
      grid-row: 7;
      grid-column: 4;
    }
    .grid-items75 {
      grid-row: 7;
      grid-column: 5;
    }
    .grid-items76 {
      grid-row: 7;
      grid-column: 6;
    }
    .grid-items77 {
      grid-row: 7;
      grid-column: 7;
    }
    .grid-items78 {
      grid-row: 7;
      grid-column: 8;
    }
    .grid-items79 {
      grid-row: 7;
      grid-column: 9;
    }
    .grid-items710 {
      grid-row: 7;
      grid-column: 10;
    }
    .grid-items81 {
      grid-row: 8;
      grid-column: 1;
    }
    .grid-items82 {
      grid-row: 8;
      grid-column: 2;
    }
    .grid-items83 {
      grid-row: 8;
      grid-column: 3;
    }
    .grid-items84 {
      grid-row: 8;
      grid-column: 4;
    }
    .grid-items85 {
      grid-row: 8;
      grid-column: 5;
    }
    .grid-items86 {
      grid-row: 8;
      grid-column: 6;
    }
    .grid-items87 {
      grid-row: 8;
      grid-column: 7;
    }
    .grid-items88 {
      grid-row: 8;
      grid-column: 8;
    }
    .grid-items89 {
      grid-row: 8;
      grid-column: 9;
    }
    .grid-items810 {
      grid-row: 8;
      grid-column: 10;
    }
    .grid-items91 {
      grid-row: 9;
      grid-column: 1;
    }
    .grid-items92 {
      grid-row: 9;
      grid-column: 2;
    }
    .grid-items93 {
      grid-row: 9;
      grid-column: 3;
    }
    .grid-items94 {
      grid-row: 9;
      grid-column: 4;
    }
    .grid-items95 {
      grid-row: 9;
      grid-column: 5;
    }
    .grid-items96 {
      grid-row: 9;
      grid-column: 6;
    }
    .grid-items97 {
      grid-row: 9;
      grid-column: 7;
    }
    .grid-items98 {
      grid-row: 9;
      grid-column: 8;
    }
    .grid-items99 {
      grid-row: 9;
      grid-column: 9;
    }
    .grid-items910 {
      grid-row: 9;
      grid-column: 10;
    }
    .grid-items101 {
      grid-row: 10;
      grid-column: 1;
    }
    .grid-items102 {
      grid-row: 10;
      grid-column: 2;
    }
    .grid-items103 {
      grid-row: 10;
      grid-column: 3;
    }
    .grid-items104 {
      grid-row: 10;
      grid-column: 4;
    }
    .grid-items105 {
      grid-row: 10;
      grid-column: 5;
    }
    .grid-items106 {
      grid-row: 10;
      grid-column: 6;
    }
    .grid-items107 {
      grid-row: 10;
      grid-column: 7;
    }
    .grid-items108 {
      grid-row: 10;
      grid-column: 8;
    }
    .grid-items109 {
      grid-row: 10;
      grid-column: 9;
    }
    .grid-items1010 {
      grid-row: 10;
      grid-column: 10;
    }
  }
</style>
