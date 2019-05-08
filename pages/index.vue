<template>
  <div>
    <el-row>
      <phone-number-component></phone-number-component>
    </el-row>
  </div>
</template>

<script>
import PhoneNumberComponent from '../components/PhoneNumberComponent.vue'

export default {
  components: {
    PhoneNumberComponent
  },
  data() {
    return {
      counter: 0
    }
  },
  watch: {
    counter() {}
  },
  methods: {
    handleClick(e) {
      if (e.index === 0 && this.counter >= 0) {
        this.counter--
      }
      if (e.index === 1 && this.counter < 5) {
        this.counter++
      }
    }
  }
}
</script>

<style scoped>
div.container {
  margin: 40px 0px;
}
span .el-button {
  border-radius: 0px;
  width: 8rem;
  background-color: black;
  color: black;
  border: 3px solid white;
  font-family: monospace;
}
</style>
