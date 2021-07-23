<template>
  <div class="time-text">{{ time }}</div>
</template>


<script>
export default {
  data: function () {
    return {
      time: "",
    };
  },
  mounted() {
    setInterval(this.showTime, 1000);
  },
  methods: {
    createTime() {
      var date = new Date();
      var h = this.formatNum(date.getHours());
      var m = this.formatNum(date.getMinutes());
      var s = this.formatNum(date.getSeconds());
      var timestring = h + ":" + m + ":" + s;
      return timestring;
    },
    showTime() {
      this.time = this.createTime();
    },
    formatNum(n) {
      return String(n).padStart(2, "0");
    },
  },
};
</script>

<style lang="scss">
html * {
  font-size: 40px;
  color: grayscale($color: #d4f12f);
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  background: black;
  text-align: center;
  margin-top: 100px;
  font-size: 72px;
}

.time-text {
  color: black;
  background-color: white;
  width: 400px;
  border: 2px inset white;
  border-radius: 12px;
  margin: auto;
}
</style>
