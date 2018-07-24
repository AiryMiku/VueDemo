<template>
  <div id="app">
    <p>原始字符串: {{ message }}</p>
    <p>计算后反转字符串: {{ reversedMessage }}</p>

    <div id="hero">
      {{ hero }}
    </div>
    <div id="axios">
      {{ hero2 }}
    </div>
  </div>

</template>

<script>
import axios from 'axios'
var url = 'http://how2j.cn/study/json.txt'
var url2 = 'http://how2j.cn/study/json.txt'

export default({
  name: 'Test',
  data () {
    return {
      message: 'Runoob!',
      hero: '',
      hero2: ''
    }
  },
  computed: {
    // 计算属性的 getter
    reversedMessage: function () {
      // `this` 指向 vm 实例
      return this.message.split('').reverse().join('')
    }
  },
  mounted: function () {
    var self = this
    fetch(url).then(function (response) {
      response.json().then(function (jsonObject) {
        var jsonString = JSON.stringify(jsonObject)
        self.hero = '通过fetch获取到的json数据：' + jsonString
      })
    }).catch(function (err) {
      console.log('Fetch错误:' + err)
    })
    axios.get(url2).then(function (response) {
      var jsonObject = response.data
      var jsonString = JSON.stringify(jsonObject)
      self.hero2 = '通过 axios 获取到的json数据：' + jsonString
    })
  }
})

</script>

<style scoped>

</style>
