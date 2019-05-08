<template lang="html">
  <div class="container">
    <el-row type="flex" justify="center">
      <el-col :md="12" :sm="16" :xs="20">
        <span v-for="(elem, index) in 11" :key="elem.key">
          <slider-component
            @onChange="e => handleChange({ value: e.value, index })"
          />
        </span>
        <el-row justify="center" type="flex" class="number-row">
          <h4>
            Phone number:
            <span>+49</span>
            <span v-for="elem in phoneNumber" :key="elem.key">
              {{ elem }}
            </span>
          </h4>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import SliderComponent from './SliderComponent.vue'

export default {
  components: {
    SliderComponent
  },
  data() {
    return {
      phoneNumber: [],
      numberObj: {}
    }
  },
  created() {
    for (let i = 0; i < 11; i++) {
      this.phoneNumber.splice(i, 1, 0)
    }
  },
  methods: {
    handleChange(e) {
      this.numberObj = {
        index: e.index,
        value: e.value
      }
      this.phoneNumber.splice(this.numberObj.index, 1, this.numberObj.value)
    }
  }
}
</script>

<style lang="css" scoped>
.el-row h4{
  font-size: 18px !important;
  font-family: monospace !important;
  color: black;
  font-weight: 300;
}
</style>
