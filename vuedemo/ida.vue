<template>
  <div class="hello">
    <div>
      <h3>这是父组件</h3>
      <p style="text-align: center;">
        <span>子组件传过来的值是{{childValue}}</span>
      </p>
      <example-child v-bind:message="parentMsg" @getChildValue="getValue"></example-child>
    </div>
  </div>
</template>

<script>
import exampleChild from './idd.vue'
export default {
  name: 'ida.vue',
  components: {
    exampleChild
  },
  data () {
    return {
      parentMsg: 'hello',
      childValue: ''
    }
  },
  mounted () {},
  methods: {
    getValue: function (val) {
      this.childValue = val
      for (var i in val) {
        this.childValue[i] = val[i]
      }
    }
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.hello {
  width: 100%;
  height: 100vh;
  background-image: url(../../dist/kaohe/static/assets/yaoqing.jpg);
  background-size: 100%;
}
.search {
  width: 100%;
  bottom: 0;
  position: fixed;
}
</style>
