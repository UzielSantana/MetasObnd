<template>
    <div>
      <h2>Atualizado do gráfico</h2>
      <form>
        <label for="data1">Meta Bia:</label>
        <input type="number" id="data1" v-model="data1">
        <label for="data2">Meta Atingida Bia :</label>
        <input type="number" id="data2" v-model="data2">
        <label for="data3">Meta Carol:</label>
        <input type="number" id="data3" v-model="data3">
        <label for="data4">Meta Atingida Carol:</label>
        <input type="number" id="data4" v-model="data4">
        <label for="data5">Meta Dani:</label>
        <input type="number" id="data5" v-model="data5">
        <label for="data6">Meta Atingida Dani:</label>
        <input type="number" id="data6" v-model="data6">
        <label for="data7">Meta Nath:</label>
        <input type="number" id="data7" v-model="data7">
        <label for="data8">Meta Atingida Nath:</label>
        <input type="number" id="data8" v-model="data8">
        <label for="data9">Meta Thay:</label>
        <input type="number" id="data9" v-model="data9">
        <label for="data10">Meta Atingida Thay:</label>
        <input type="number" id="data10" v-model="data10">
        

        <button type="button" @click="updateChart">Atualizar</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        data1: 0,
        data2: 0,
        data3: 0,
        data4: 0,
        data5: 0,
        data6: 0,
        data7: 0,
        data8: 0,
        data9: 0,
        data10: 0,
      
      }
    },
    methods: {
      updateChart() {
        this.$emit('update-chart', {
          data1: this.data1,
          data2: this.data2,
          data3: this.data3,
          data4: this.data4,
          data5: this.data5,
          data6: this.data6,
          data7: this.data7,
          data8: this.data8,
          data9: this.data9,
          data10: this.data10,

        })
      }
    }
  }
  </script>