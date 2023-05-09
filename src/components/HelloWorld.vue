<template>

<div>
  
    <div class="chart">
      <div class="wrapper">
    <div class="sidebar">
      <!-- conteúdo da barra lateral -->
    </div>
    <div class="main-content">
      <!-- conteúdo principal -->
    </div>
  </div>
      <canvas id="myChart"></canvas>
    </div>
  </div>
  
<div>
  <div class>   </div> 
  
<br>
  <h1> Essas são as metas individuais de destravamentos no Onboarding Enterprise</h1>
 <div class="grafico1"> <canvas id="myChart"></canvas> </div>

    <h1 class="h12">Destravamentos - Ativados - Travados - Desaparecidos </h1>
 <div> <canvas id="myChart2"></canvas> </div> 
</div>


  <div>
    <div class="sidebar">
      <Sidebar @update-chart="updateChart"></Sidebar>
    </div>
    <div class="chart">
      <canvas id="myChart"></canvas>
    </div>
    <br>
    <h1>Essas são as metas individuais de destravamentos no Onboarding Enterprise</h1>
    <div class="grafico1">
      <canvas id="myChart2"></canvas>
    </div>
    <h1 class="h12">Destravamentos - Ativados - Travados - Desaparecidos </h1>
    <div>
      <canvas id="myChart3"></canvas>
    </div>
  </div>
</template>
<script>
import Chart from 'chart.js/auto';
import Sidebar from './SideBar.vue'

export default {
  components: {
    Sidebar,
  },
  mounted() {
    this.drawChart();
  },
  methods: {
    drawChart() {
      const ctx = document.getElementById('myChart');
      this.chart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: ['Bia', 'Carol', 'Dani', 'Nath', 'Thay', 'Uzi'],
          datasets: [
            {
              label: 'Meta Realizada',
              data: [1, 5, 1, 3, 3, 2, 5],
              backgroundColor: '#FF6384', // cor da barra para 'Meta Realizada'
              borderWidth: 1,
              width: 20,
            },
            {
              label: 'Meta Não Realizada',
              data: [4, 2, 4, 2, 2, 3, 4],
              backgroundColor: '#36A2EB', // cor da barra para 'Meta Não Realizada'
              borderWidth: 1,
              width: 20,
            },
         
            /*
            {
              label: 'Meta Parcialmente Realizada',
              data: [2, 3, 3, 1, 3, 3, 3],
              backgroundColor: '#FFCE56', // cor da barra para 'Meta Parcialmente Realizada'
              borderWidth: 1,
              width: 20,
            }, */
          ] 
        },
        options: {
          layout: {
            padding: 90
          },
          scales: {
            y: {
              beginAtZero: true
            }
          }
        }
      });
    },
    updateChart(data) {
      // Atualize o gráfico com base nos dados recebidos da barra lateral
      this.chart.data.datasets[0].data[0] = data.data1;
      this.chart.data.datasets[1].data[0] = data.data2;
      this.chart.data.datasets[0].data[1] = data.data3;
      this.chart.data.datasets[1].data[1] = data.data4;
      this.chart.data.datasets[0].data[2] = data.data5;
      this.chart.data.datasets[1].data[2] = data.data6;
   

 
      this.chart.update();
      console.log(data)
    }
  }
};
</script>

<style >



.wrapper {
  display: flex;
  height: 100%;
}

.sidebar {
  margin:0;
  width: 200px;
  background-color: #ccc;
  padding: 20px;
}

.main-content {
  flex: 1;
  background-color: #fff;
  padding: 20px;
}



body {


  background-color: rgb(223, 214, 214);
  
}

img {

  margin-left: 50px;
  margin-right: -50px;
  margin-top: 30px
  wi
  
}

h1 { 

  margin-left: -80px ;
  margin-top: 40px;
  margin-bottom:-50px;
  padding-bottom: - 70px;

  color:rgb(222, 222, 35);
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}


.h12 { 

margin-left: -80px ;
margin-top:40px;
margin-bottom:-50px;
padding-bottom: - 70px;
color:rgb(222, 222, 35);

font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}


.grafico {

  max-width: 200px;
}

canvas {

  width: 100px;
}

.imgs {

  display: flex;
}
</style>