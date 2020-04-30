<template>
  <div id="game" @click="clickCell">
    <div v-for="box in boxes"
        :key="box.id"
        class="box"
        :style="{ top: box.y + 'px', left: box.x + 'px' }">
      {{ box.id }}
    </div>
    <!-- <div v-for="i in 100" :key="i" class="r">
      <div v-for="j in 100" :key="j" class="c">
        r{{i}}
        <br>
        c{{j}}
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    numBoxes: 0,
    boxes: []
  }),
  methods: {
    clickCell(event) {
        // e = Mouse click event.
  var rect = event.target.getBoundingClientRect();
  var x = event.clientX - rect.left; //x position within the element.
  var y = event.clientY - rect.top;  //y position within the element.

        console.log(event)
              // clientX/Y gives the coordinates relative to the viewport in CSS pixels.
        console.log("event.clientX: ", event.clientX); // x coordinate
        console.log("event.clientY: ", event.clientY); // y coordinate

        // pageX/Y gives the coordinates relative to the <html> element in CSS pixels.
        console.log("event.pageX: ", event.pageX); 
        console.log("event.pageY: ", event.pagey); 
                // screenX/Y gives the coordinates relative to the screen in device pixels.
        console.log("event.screenX: ", event.screenX);
        console.log("event.screenY: ", event.screenY);

        let xPos = Math.floor(x / 40) * 40;
        let yPos = Math.floor(y / 40) * 40;

        this.boxes.push({
          id: this.numBoxes,
          x: xPos,
          y: yPos
        })

        this.numBoxes++;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.box {
  background: red;
  height: 40px;
  width: 40px;
  position: absolute;
  display: block;
}

#game {
  position: relative;
  width: 10000px;
  height: 10000px;
  color: orange;
  /* background-color: #555; */

  background:
    linear-gradient(-90deg, rgba(0,0,0,.05) 1px, transparent 1px),
    linear-gradient(rgba(0,0,0,.05) 1px, transparent 1px), 
    linear-gradient(-90deg, rgba(0, 0, 0, .04) 1px, transparent 1px),
    linear-gradient(rgba(0,0,0,.04) 1px, transparent 1px),
    linear-gradient(transparent 3px, #f2f2f2 3px, #f2f2f2 78px, transparent 78px),
    linear-gradient(-90deg, #aaa 1px, transparent 1px),
    linear-gradient(-90deg, transparent 3px, #f2f2f2 3px, #f2f2f2 78px, transparent 78px),
    linear-gradient(#aaa 1px, transparent 1px),
    #f2f2f2;
  background-size:
      8px 8px,
      8px 8px,
      40px 40px,
      40px 40px,
      40px 40px,
      40px 40px,
      40px 40px,
      40px 40px;
}
/* background: adjust-hue($base-color, $offset + $spectrum / $num-colors * $i); */
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: monospace;
}

/* body {

} */

.r {
  display: flex;
  width: 8000px;
  /* background: blue; */
  padding: 0;
}
.r .c {
  border: 1px outset grey;
  height: 40px;
  width: 40px;
  background: red;
  display: inline-block;
}
.r .c:nth-child(0) {
  background: #cddbd6;
}
.r .c:nth-child(1) {
  background: #d5d4bd;
}
.r .c:nth-child(2) {
  background: #bdd9d0;
}
.r .c:nth-child(3) {
  background: #dccace;
}
.r .c:nth-child(4) {
  background: #ded1ba;
}
.r .c:nth-child(5) {
  background: #cfcabe;
}
.r .c:nth-child(6) {
  background: #d4c7d7;
}
.r .c:nth-child(7) {
  background: #d8ced5;
}
.r .c:nth-child(8) {
  background: #cdd8c1;
}
.r .c:nth-child(9) {
  background: #bacbd6;
}
.r .c:nth-child(10) {
  background: #d1d3c8;
}
.r .c:nth-child(11) {
  background: #d2d2c7;
}
.r .c:nth-child(12) {
  background: #dac4cc;
}
.r .c:nth-child(13) {
  background: #d3c4de;
}
.r .c:nth-child(14) {
  background: #c5bad2;
}
.r .c:nth-child(15) {
  background: #bccfcd;
}
.r .c:nth-child(16) {
  background: #c7d2be;
}
.r .c:nth-child(17) {
  background: #dbc4dd;
}
.r .c:nth-child(18) {
  background: #c0c3d9;
}
.r .c:nth-child(19) {
  background: #cad8cf;
}
.r .c:nth-child(20) {
  background: #d2c9dd;
}
.r .c:nth-child(21) {
  background: #bac3d5;
}
.r .c:nth-child(22) {
  background: #c1bdca;
}
.r .c:nth-child(23) {
  background: #c2dbe1;
}
.r .c:nth-child(24) {
  background: #c0c1cf;
}
.r .c:nth-child(25) {
  background: #d2c3bf;
}
.r .c:nth-child(26) {
  background: #cdc2c2;
}
.r .c:nth-child(27) {
  background: #d7c7dd;
}
.r .c:nth-child(28) {
  background: #d0bbd4;
}
.r .c:nth-child(29) {
  background: #e0d6d5;
}
.r .c:nth-child(30) {
  background: #bbd9d3;
}
.r .c:nth-child(31) {
  background: #e0e0db;
}
.r .c:nth-child(32) {
  background: #c1dadb;
}
.r .c:nth-child(33) {
  background: #d6c6df;
}
.r .c:nth-child(34) {
  background: #c5c8c3;
}
.r .c:nth-child(35) {
  background: #bdcbd4;
}
.r .c:nth-child(36) {
  background: #c6dfd2;
}
.r .c:nth-child(37) {
  background: #cebbde;
}
.r .c:nth-child(38) {
  background: #bdbebe;
}
.r .c:nth-child(39) {
  background: #d5c2db;
}
.r .c:nth-child(40) {
  background: #c0d7cd;
}
.r .c:nth-child(41) {
  background: #bad9ba;
}
.r .c:nth-child(42) {
  background: #d9bdbd;
}
.r .c:nth-child(43) {
  background: #c0bbbc;
}
.r .c:nth-child(44) {
  background: #c4e1dc;
}
.r .c:nth-child(45) {
  background: #d0d9bc;
}
.r .c:nth-child(46) {
  background: #dcbcc9;
}
.r .c:nth-child(47) {
  background: #c7cdc7;
}
.r .c:nth-child(48) {
  background: #e1d1c7;
}
.r .c:nth-child(49) {
  background: #d2bed4;
}
.r .c:nth-child(50) {
  background: #d8bfe1;
}
.r .c:nth-child(51) {
  background: #dfc4bc;
}
.r .c:nth-child(52) {
  background: #c5c2d0;
}
.r .c:nth-child(53) {
  background: #bbe1c2;
}
.r .c:nth-child(54) {
  background: #c5c2be;
}
.r .c:nth-child(55) {
  background: #c5c6dd;
}
.r .c:nth-child(56) {
  background: #d8caca;
}
.r .c:nth-child(57) {
  background: #c5d3c3;
}
.r .c:nth-child(58) {
  background: #d7ccce;
}
.r .c:nth-child(59) {
  background: #d2c1c9;
}
.r .c:nth-child(60) {
  background: #bdc7da;
}
.r .c:nth-child(61) {
  background: #c6c7cd;
}
.r .c:nth-child(62) {
  background: #ccc6d9;
}
.r .c:nth-child(63) {
  background: #cacdcf;
}
.r .c:nth-child(64) {
  background: #dbe0df;
}
.r .c:nth-child(65) {
  background: #cce0ce;
}
.r .c:nth-child(66) {
  background: #d9ddbe;
}
.r .c:nth-child(67) {
  background: #d8bed8;
}
.r .c:nth-child(68) {
  background: #cbbec6;
}
.r .c:nth-child(69) {
  background: #d6c3c5;
}
.r .c:nth-child(70) {
  background: #dbbfe1;
}
.r .c:nth-child(71) {
  background: #bcc9cc;
}
.r .c:nth-child(72) {
  background: #d1cadb;
}
.r .c:nth-child(73) {
  background: #d6c4e0;
}
.r .c:nth-child(74) {
  background: #c8d3d1;
}
.r .c:nth-child(75) {
  background: #c3dccc;
}
.r .c:nth-child(76) {
  background: #ccc0bf;
}
.r .c:nth-child(77) {
  background: #dec8da;
}
.r .c:nth-child(78) {
  background: #bdbad9;
}
.r .c:nth-child(79) {
  background: #cec2c2;
}
.r .c:nth-child(80) {
  background: #d6bfdc;
}
.r .c:nth-child(81) {
  background: #bdd0d7;
}
.r .c:nth-child(82) {
  background: #c3d9dd;
}
.r .c:nth-child(83) {
  background: #bde1da;
}
.r .c:nth-child(84) {
  background: #bebadf;
}
.r .c:nth-child(85) {
  background: #bbc4da;
}
.r .c:nth-child(86) {
  background: #c2d6d5;
}
.r .c:nth-child(87) {
  background: #dde0df;
}
.r .c:nth-child(88) {
  background: #dbc2ce;
}
.r .c:nth-child(89) {
  background: #c6bdd3;
}
.r .c:nth-child(90) {
  background: #d9e1cc;
}
.r .c:nth-child(91) {
  background: #c2c1e0;
}
.r .c:nth-child(92) {
  background: #d7d9cb;
}
.r .c:nth-child(93) {
  background: #c2bdc1;
}
.r .c:nth-child(94) {
  background: #e1c2c6;
}
.r .c:nth-child(95) {
  background: #d2cdd4;
}
.r .c:nth-child(96) {
  background: #c2e0bf;
}
.r .c:nth-child(97) {
  background: #bcc4d3;
}
.r .c:nth-child(98) {
  background: #ccdac5;
}
.r .c:nth-child(99) {
  background: #dbdfd4;
}
</style>
