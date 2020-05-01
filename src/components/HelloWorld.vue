<template>
  <div class="grid">
    <input type="text" v-model="result" placeholder="0">
    <button @click="input(number)" v-for="(number, key) in numbers" :key="key" class="cell num">{{number}}</button>
    <button @click="input(opt)" v-for="(opt, key) in operations" :key="key" class="cell op">{{opt}}</button>
    <button @click="reset" class="cell op">R</button>
    <button @click="calc()" class="cell op">=</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      result: '',
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
      operations: ['+', '-', '*', '/']
    }
  },
  methods: {
    input(char) {
      this.result = this.result.toString()
        this.result += char;
    },
    reset() {
      this.result = ''
    },
    calc() {
      this.result = eval(this.result)
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

input[type="text"] {
  width: 200px;
  border: 0;
  color: #243849;
  font-size: 18px;
  padding: 5px 5px;
  text-align: right;
  outline: none;
  border: 1px solid black;
  padding: 5px 0;
}
.grid {
  display: flex;                       
  flex-wrap: wrap;  
  justify-content: space-around;
  width: 200px;
  margin: 0 auto;
  
}
.cell {
  flex: 33%;                       
  height: 50px;
  font-size: 18px;
  border: none;
}
.num {
  background-color: #243849;
  color: #fff;
  font-weight: 400;
}
.cell:hover{
  background-color: #182530;
}
.op {
  background-color: #ff9900;
  color: #243849;
}

</style>
