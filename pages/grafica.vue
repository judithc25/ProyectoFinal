<template>
  <v-container>
    <v-row>
      <!-- Purchases Report -->
      <v-col cols="12" md="6" lg="4">
        <v-card>
          <v-card-title>Purchases Reports</v-card-title>
          <v-card-text>
            <canvas id="purchasesChart" />
          </v-card-text>
        </v-card>
      </v-col>

      <!-- Sells Report -->
      <v-col cols="12" md="6" lg="4">
        <v-card>
          <v-card-title>Sells Reports</v-card-title>
          <v-card-text>
            <canvas id="sellsChart" />
          </v-card-text>
        </v-card>
      </v-col>

      <!-- Stock Report -->
      <v-col cols="12" md="6" lg="4">
        <v-card>
          <v-card-title>Stock Reports</v-card-title>
          <v-card-text>
            <canvas id="stockChart" />
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import { onMounted } from 'vue'
import Chart from 'chart.js/auto/auto.esm.js'

export default {
  name: 'DashboardCharts',
  setup () {
    // Función auxiliar para crear gráficos
    const createChart = (id, config) => {
      const ctx = document.getElementById(id)
      if (ctx) {
        return new Chart(ctx, config)
      }
      // eslint-disable-next-line no-console
      console.log('Mensaje de depuración')
      return null
    }

    // Inicializar gráficas
    const initializeCharts = () => {
      // Purchases Chart
      createChart('purchasesChart', {
        type: 'line',
        data: {
          labels: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          datasets: [
            {
              label: 'Purchases',
              data: [1500, 2200, 800, 2500, 1800, 1600, 900],
              borderColor: '#3f51b5',
              backgroundColor: 'rgba(63, 81, 181, 0.1)',
              tension: 0.3,
              fill: true
            }
          ]
        },
        options: {
          responsive: true,
          plugins: {
            legend: { display: false }
          }
        }
      })

      // Sells Chart
      createChart('sellsChart', {
        type: 'doughnut',
        data: {
          labels: ['Chrome', 'IE', 'Firefox', 'Safari', 'Opera'],
          datasets: [
            {
              data: [5000, 2000, 3000, 4000, 1000],
              backgroundColor: ['#3f51b5', '#ff9800', '#4caf50', '#f44336', '#00bcd4']
            }
          ]
        },
        options: {
          responsive: true,
          plugins: {
            legend: { position: 'right' }
          }
        }
      })

      // Stock Chart
      createChart('stockChart', {
        type: 'bar',
        data: {
          labels: ['Firefox', 'Chrome', 'Opera', 'Safari', 'IE'],
          datasets: [
            {
              label: 'Stock',
              data: [8000, 13000, 9000, 11000, 6000],
              backgroundColor: ['#4caf50', '#3f51b5', '#f44336', '#00bcd4', '#ff9800']
            }
          ]
        },
        options: {
          responsive: true,
          plugins: {
            legend: { display: false }
          }
        }
      })
    }

    // Montar gráficas al renderizar el componente
    onMounted(() => {
      initializeCharts()
    })
  }
}

</script>

  <style>
  canvas {
    max-height: 300px;
  }
  </style>
