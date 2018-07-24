<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="foo">点我啊笨蛋</button>
    <br>
    <div id="table1">
      <table align="center">
        <tr class="firstLine">
          <td>名字</td>
          <td>HP</td>
        </tr>
        <tr v-for="hero in heros" :key="hero.name">
          <td>{{hero.name}}</td>
          <td>{{hero.hp}}</td>
        </tr>
        <tr>
          <td>
            <input v-model.lazy="input" placeholder="please input"/>
          </td>
          <td>
            {{ input }}
          </td>
        </tr>
      </table>
    </div>

    <router-link to="/Test">用户管理</router-link>

  </div>
</template>

<script>

var dataList = [
  {name: '盖伦', hp: 341},
  {name: '提莫', hp: 225},
  {name: '安妮', hp: 427},
  {name: '死歌', hp: 893}
]
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '你好旅行者',
      heros: dataList,
      input: ''
    }
  },
  methods: {
    foo: function () {
      alert('666')
    }
  }
}
// new Vue({
//   el: '#app',
//   data: {
//     message: 'runoob'
//   },
//   filters: {
//     capitalize: function (value) {
//       if (!value) return ''
//       value = value.toString()
//       return value.charAt(0).toUpperCase() + value.slice(1)
//     }
//   }
// })
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
table tr td{
  border:1px solid gray;
}
table{
  border-collapse:collapse;
  width:300px;
}
tr.firstLine{
  background-color: lightGray;
}
</style>
