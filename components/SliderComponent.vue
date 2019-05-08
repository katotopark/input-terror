<template lang="html">
  <div class="container">
    <el-slider
      v-model="inputVal"
      :max="9"
      :steps="1"
      @change="$emit('onChange', { value: inputVal })"
    >
    </el-slider>
  </div>
</template>
<script>
export default {
  data() {
    return {
      inputVal: 0
    }
  },
  methods: {}
}
</script>

<style lang="css">
div.container {
  margin: 10px auto;
}
.el-slider__button {
  border: 2px solid black;
  border-radius: 0px;
  background-color: white;
  padding: 10px;
}
.el-slider__bar {
  background-color: black;
  border-radius: 0px;
}
.el-slider__runway {
  border-radius: 0px;
  background-color: #696969;
}
</style>
