<template>
  <div class="time-text">{{ time }}</div>
</template>


<script>
export default {
  data: function () {
    return {
      time: '33',
      mins: "",
    };
  },
  mounted() {
    // setInterval(this.setTime, 500);
    // setInterval(this.getTime, 1000);
    setInterval(this.showTime, 1000);
  },
  methods: {
    // setTime() {
    //   this.time = Date();
    // },
    // getTime() {
    //   this.mins = this.time.getMinutes();
    // },
    // createMin() {
    //   this.mins = this.time[2]
    // },
    createTime() {
      var date = new Date();
      var h = date.getHours(); // 0 - 23
      var m = date.getMinutes(); // 0 - 59
      var s = date.getSeconds();
      var sNew = s.toString()
      // if (sNew.length<2) {
      //   console.log('lesss')
      //   sNew= 0+sNew
      //   console.log('im snew', sNew)
      //   s=parseInt(sNew)
      // }
      //console.log(sNew)
      var timestring = h + ":" + m + ":" + s;
      return timestring;
    },
    showTime() {
      this.time = this.createTime();
    },
  },
};
</script>

<style lang="scss">
html * {
  font-size: 40px;
  color: grayscale($color: #d4f12f);
  font-family: Arial !important;
  background: black;
  text-align: center;
  margin-top: 100px;
}

.time-text {
  color: white;
  border: inset 4px grey;
  border-radius: 8px;
  padding: 24px;
}
</style>
