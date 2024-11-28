<template>
  <v-container>
    <v-row class="texto">
      <v-col>
        <h3>Pharmary Management</h3>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="central2" md="2">
        <h3>Total Customer</h3>
      </v-col>
      <v-col class="central3" md="2">
        <h3>Total Medicine</h3>
      </v-col>
      <v-col class="central4" md="2">
        <h3>Total Manufactures</h3>
      </v-col>
    </v-row>
    <v-row class="central">
      <v-col md="5">
        <v-btn class="boton1">
          Create Inovoice
        </v-btn>
      </v-col>
      <v-col md="5">
        <v-btn class="boton1">
          Supplier
        </v-btn>
      </v-col>
      <v-col md="2">
        <v-btn class="boton1">
          Medicine
        </v-btn>
      </v-col>
    </v-row>
    <v-row class="texto3">
      <h3 class="titulo">
        Out of Stock
      </h3>
      <p class="parrafo">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto, culpa.
      </p>
      <v-simple-table class="tabla">
        <thead>
          <tr>
            <th>ID</th>
            <th>Drug Name</th>
            <th>Expire Date</th>
            <th>Manufacture Date</th>
            <th>Price</th>
            <th>QTY</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in suppliers" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>{{ item.date }}</td>
            <td>{{ item.mdate }}</td>
            <td>{{ item.price }}</td>
            <td>{{ item.qty }}</td>
            <td>
              <v-icon>mdi-status</v-icon>
            </td>
          </tr>
        </tbody>
      </v-simple-table>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'InspirePage'
}
</script>

<style scoped>
.central4 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 20%;
  margin-top: 2%;
}
.central3 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 18%;
  margin-right: 2%;
  margin-top: 2%;
}
.central2 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 5%;
  margin-right: 2%;
  margin-top: 2%;
}
.central {
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
  margin-top: 2%;
}
.parrafo {
  margin-top: 6%;
}
.tabla {
  margin-top: 1%;
  width: 90%;
  margin-left: 3%;
  margin-right: 1%;
}
.titulo {
  margin-top: 1%;
  margin-left: 2%;
}
.texto {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
}
.texto3 {
  background-color:rgb(247, 244, 241);
  border-radius: 13px;
  margin-left: 1.6%;
  margin-right: 1.6%;
  margin-top: 5%;
}

.boton1 {
  margin-top: 3%;
  margin-left: 3%;
  background: linear-gradient(-90deg,#7f7694, #8e81cc);
  border-radius: 10px;
  margin-bottom: 6%;
  height: 1589px;
}

</style>
